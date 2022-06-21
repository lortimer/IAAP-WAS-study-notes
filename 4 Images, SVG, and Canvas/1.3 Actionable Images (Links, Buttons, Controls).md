# Actionable Images (Links, Buttons, Controls)

Often, these are icons that act as buttons

## All actionable images (e.g., links, buttons, controls) MUST have alternative text

The alt text should describe the destination, purpose, or function, not the image or icon.

Don't include "link to" or "button" as the screen reader announces those things.

### Good Example
"Home" or "Home Page" are approriate in the following link/image

```html
<a href="#"><img src="home.png" alt="Home" width="113"></a>
```

## The alternative text for actionable images MUST be meaningful (accurately conveying the purpose or result of the action)

Again, the alt text should describe the purpose of clicking that image. There's no need to describe the image, to a blind user, it is just a link or button.

## Alternative text SHOULD NOT include words that identify the element as a link, graphic, or image

## The length of the alternative text for actionable images SHOULD be concise (no more than about 150 characters)