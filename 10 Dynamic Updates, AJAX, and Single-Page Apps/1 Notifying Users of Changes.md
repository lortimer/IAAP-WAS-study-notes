# 1 Notifying Users of Changes

## Status messages MUST be programmatically determinable through role or properties such that they can be presented to the user by assistive technologies without receiving focus

Dynamic changes to a page are easy to see, but there is no automatic system for notifying screen-reader users that they have occurred. The worst thing that can happen is a user clicks a button and hears nothing, but that happens all the time.

## Option 1: Load or Reload Page

One of the easiest ways to alert screen reader users is to load a new page or reload the current page. It requires no Javascript. When a page is loaded, screen readers do the following:

- Read the page title
- Summarize the features on the page
- Start reading from the top of the page

Users know this happens, so they understand they have taken action that will read them new content.

### Accessibility Considerations

- Page title should reflect the page content AND the result of user actions.
  - When reloading a page with a form that had validation errors when submitted, the title should reflect that: "Contact Us: Error, please correct 3 errors in the form"
- Make it easy to navigate to the main content.
  - If the new content is buried in the middle of the page, event a "skip to content" link won't work well, because keyboard users will then have to tab through the content to find the new stuff.

## Option 2: Move the Focus

When new content appears, it _may_ be appropriate to send focus to the new content. A classic example is a modal dialog.

### Accessibility Considerations

**The container where the focus is sent must have tabindex="-1"**. If the container is not set to tabindex="-1", the focus will not arrive successfully in all browsers, and screen readers may not read the text.

**The container must not be empty**. You would not want to send the focus to an empty <div> or any other empty container, because even if the focus arrives successfully, the screen reader will have nothing to read. The screen reader will be silent, defeating the purpose of sending the focus in the first place.

**Don't move the focus unexpectedly**. Sending the focus should always be the result of either a user-initiated action, or some other critical event that demands the user's immediate attention. Don't send the focus just to make an announcement if moving the focus would disrupt the user's actions, or if the disruption is not critical. **Use ARIA live regions to make announcements that do not steal the keyboard focus**.

**Sending the focus must be the last event, and it will probably be necessary to delay before sending the focus**. When content is loaded via AJAX, it sometimes takes a moment AFTER the AJAX is done loading for the AJAX content to be available to screen readers, especially if JavaScript is used to manipulate the new content after it is loaded, and especially if the keyboard focus happens to already be within the area that you intend to send the focus (either on the element itself or on a descendent of it). If you send the focus too soon, the DOM node may not be available yet, or it may be empty, causing the screen reader to say nothing when the focus arrives on the node.

Test the process in various screen readers and browsers, **and with a slow connection**. If any of them fail to read the content when the focus arrives, add a delay (1 to 2 seconds is plenty) before sending the focus. In fact, to be on the safe side, it is best to add a delay with all AJAX load events before sending the focus.

### Good Example

It's usually preferable to send the focus to the heading at the top of new content rather than a container, because some screen readers will read the whole container non-stop

The following example uses JQuery.

```html
<div id="decContainer"></div>
<script>   
$("#decButton").click(function(){
  $.ajax({
    url: "assets/html/module-dynamic/ajax/declaration.html", 
    type:'GET',
    cache: false,
    success: function(result){
      $("#decContainer").show().html(result);
      var decHeading = $("#decContainer h2:first");
      /* set tabindex="-1" so the heading can receive keyboard focus */
      decHeading.attr('tabindex','-1');
      setTimeout(function(){ 
        /* move focus to the heading after a delay of 1 second */
        $("#decContainer h2:first").focus(); 
      }, 1000);
    }
  });
}); 
</script>
```

## Option 3: ARIA Live

ARIA Live announcements allow the page to read the user an announcement without loading a page or moving focus. For custom widgets, they maybe the only way to keep the user apprised of changes.

ARIA Live regions are containers like a `div` marked as live regions. They start empty, and Javascript inserts text when announcement needs to be made. Screen readers speak the text because they are watching for changes to live regions.

### ARIA Live Types

There are two types of ARIA Live announcements:

- `aria-live="assertive"`
  - Meant to interrupt the screen reader immediately to make the announcement.
- `aria-live="polite"`
  - Meant to wait until the screen reader finishes reading the current sentence or item. Essentially, the announcement is enqueued behind what the screen reader is already doing.

Users can customize their screen reader's reaction to live events.

### ARIA Live Roles

Live regions can be created by giving special roles to containers. [See this page for documentation](https://www.w3.org/TR/wai-aria-1.1/#aria-live). The role is applied to a container instead of `aria-live`. They include:

-`role="alert"` - Assertive, speaks "alert" before reading the text
-`role="log"` - Polite, used for chat logs, messaging history, etc. Reading order matters. Old information may disappear
- `role="marquee"` - Similar to log, for information that changes quickly. Reading order doesn't matter. Implicitly have `aria-live="off"`, so they won't announce changes
-`role="status"` - Polite, like alert but not as important.
-`role="timer"` - Text content indicates current value of a timer of some kind. Implicitly have `aria-live="off"`, so they won't announce changes

### Good Example

In this example, clicking a button will create text in a live region for 3 seconds, then hide it.

```html
<p><button id="liveButton">Create announcement</button>
<span id="liveRegion" aria-live="assertive"></span></p>
<p><button id="liveButton">Create announcement</button></p>
<script>
$('#liveButton').click(function(){
  var live = $('#liveRegion');
  live.css({
    'display':'inline-block',
    'background-color':'#fff5bc',
    'padding':'0px 4px'
  }).text('Hooray for accessibility!');
  setTimeout(function(){ 
    live.text('');
    live.removeAttr('style');
  }, 3000);
});
</script>
```



### Accessibility Considerations

**The ARIA live region must be present and empty before making an announcement.** If it isn't on the page, the accessibility API can't track changes to it. If you insert a live region after page load, you have to delay announcements by at least 1 second.

**ARIA live announcements should be brief.** Announcements can be interrupted, and if it is interrupted, it cannot be retrieved.

**Remove the announcement soon after it is inserted (in most cases).** If a users comes across the stale announcement text, they may think the page is making a new announcement.

**If the announcement is not meant to be seen, hide with CSS clip.**