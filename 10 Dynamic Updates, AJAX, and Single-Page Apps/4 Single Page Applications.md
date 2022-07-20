# 4 Single Page Applications

Single Page apps make websites faster by not loading a new page every time, but replacing content on the page. The main accessibility challenges with them are:

- Notifying users when new content is loaded (silence is bad)
- Managing keyboard focus
  - When a new page is loaded in an SPA, the content the focus was on previously disappears. This usually results in focus being lost.

## Screen reader users SHOULD be made aware when new "pages" are loaded in single-page applications.

### Move focus to the new content

- Container must have `tabindex="-1"`
- The focus MUST be temporarily moved, then sent to the correct destination.
  - This is because if the focus is already on the container where you send focus, some screen readers will not read the new content of the container.
- There MUST be a delay before sending the focus to the final destination
  - Similar to above, some screen readers are bad about losing focus on AJAX content if focus is sent too soon. Wait about 1 second.
- The focus SHOULD be sent to a heading at the beginning of the AJAX content
  - The page title isn't read on change, so this can substitute for that.

### Announce it with ARIA live.

IF it's most appropriate to keep focus on the button or link that triggered the new content, this option is ok.

- Optional: Confirm that the action is in progress. Like "Page Loading"
- Confirm the result of the action (success or failure message)
- Keep the message brief
- Choose either assertive or polite
- Optional: provide (brief) instructions related to the new content

### BONUS OPTION

In React Router, `Link` components take an optional attribute `reloadDocument` that makes your React Single-Page App behave like a Server-Rendered app. It reloads the whole document when a link with that attribute is clicked, nullifying all of the focus issues of an SPA.

```html
<Link to={"/home"} reloadDocument>Click Here</Link>
```

## The browser history MUST be updated when an AJAX event is the result of clicking on a link OR if the event is such that a user would expect to be able to use the "back" button after the event

This usually happens automatically with a provided "router" library, like React Router.

## The page MUST respond appropriately when the user activates back or forward functionality in the browser

To implement your own handling of the back and forward buttons, use the `window`'s `popstate` event.

## Good Example

https://dequeuniversity.com/assets/html/module-dynamic/singlepage/good/index.html

```javascript
$(function () {

  var currentContent = $('#innerContent');
  var currentHeading = $('#contentHeading');
  var newTitle;
  var newHeading;
  var newContent;

  var load = function (newUrl) {
    /* get AJAX content */
    $.get(newUrl).done(function (data) {
	
    /* Parse the page into variables to insert separately */
    newTitle = $(data).filter('title').html();
    var newMain = $(data).filter('main').html();
    newHeading = $(newMain).filter('h1').html();
    newContent = $(newMain).filter('#innerContent').html();
		
    /* update document with AJAX content variables */
    document.title = newTitle;
    currentContent.html(newContent);
    currentHeading.html(newHeading);	
    });
  }

  function focusH1(){
    /* Set focus temporarily on an empty div, 
	to force screen readers (especially VoiceOver)
	to read the focused item if the focus was already
	on that same item before we re-sent the focus to it */
    $('#tempFocus').focus();
	  
    /* Set focus on the h1 at the beginning of the content
    after a brief delay (the delay is mostly for iOS;
    sometimes shorter delays work, but they are risky 
    in iOS, so a minimum of 1 second is recommended) */
    setTimeout(function(){ 
      currentHeading.focus(); 
    }, 1000);
  };

  function emptyOld() {
    /* empty the original content 
    that is about to be replaced
    so that iOS doesn't read old information */
    $('#contentHeading, #innerContent').empty();
  }

  $(document).on('click', 'a', function (e) {
    /* activate the functions when a link is clicked */
	  
    /* don't let links act like regular links */
    e.preventDefault();

    emptyOld();

    newUrl = $(this).attr("href");
    load(newUrl);
		
    /* update the browser history */
    history.pushState({
      url: newUrl,
      title: newTitle
    }, newTitle, newUrl);

    focusH1();
  });

  $(window).on('popstate', function (e) {
    var state = e.originalEvent.state;

    if (state !== null) {
      /* activate the functions if a popstate is detected,
      e.g. if "back" or "forward" are used in the browser */

      emptyOld();

      document.title = state.title;

      load(state.url);
			
      focusH1();
    } 
		
    else {
      /* if the page loads normally 
      (not by clicking on a link or by 
      using the back/forward buttons) */
    }		
  });
});
```