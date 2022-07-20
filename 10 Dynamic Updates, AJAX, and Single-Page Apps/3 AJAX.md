# 3 AJAX

**A**synchronous **J**avascript **A**nd **X**ML - AJAX is a term for web code that asynchrounously loads and builds parts of a page. In modern web apps, this is usually code that calls APIs to get data with which to populate a page.

## Lazy Loading

Lazy loading is loading resources as they are needed, especially when they are not on screen on page load.

As the course describes it, lazy loading is actually loading parts of the page separately at page-load time. I disagree with the definition, but agree that loading the skeleton of the page then loading the data for the page gives a better user experience generally.

### Placeholders for AJAX content SHOULD inform screen reader users that the content is loading

This can be the whole main content, or smaller sections/components.

```html
<img src="spinning.gif" alt="Content loading" width="36" height="36">
```

### "Lazy loading" AJAX content SHOULD NOT be announced as it loads.

Except on slow connections or when a server is responding slowly, the content will usually load before a user has a chance to navigate focus to it.

However, you should manage focus when a loading indicator disappears and content takes its place

## Infinite Scrolling

Also called "Lazy Loading" by most developers. Like a Facebook feed or Reddit, the page loads new content as the user scrolls.

### An "infinite scrolling" feature MUST allow users to reach all areas of the page with the keyboard.

New content loading automatically gets inserted into the tab order, so users can't reach the bottom of the page. That's why infinite scrolling apps have no bottom, and all the stuff you would find in a footer is redistributed to the top and sides of the page.

### An "infinite scrolling" feature MAY be activated only at the user's request

Instead of making the load automatic, you can let users click a button to load more content, or at least opt into this.

## Interstitial Views

Essentially, loading views. Like when you buy plane tickets and it takes you to a page that tells you not to refresh.

### Screen reader users MUST be informed when a web page launches an interstitial view, a progress indicator, or enters into a paused or busy state

Screen-reader users need to hear a reaction to triggering an action! You have to move focus to a loading view or announce it via ARIA live