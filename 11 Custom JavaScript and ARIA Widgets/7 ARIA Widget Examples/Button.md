# Button

In most circumstances, using a native HTML `<button>` or `<input type="submit">` element is a better choice than creating a custom ARIA button, but there are use cases where an ARIA button can be appropriate, such as when styling a standard `<button>` is too difficult in the range of target browsers under certain circumstances, or when retrofitting legacy markup that could be problematic to convert to standard `<button>` elements.

## Expected Operation

### Activation

Any of the following will activate the button: mouse click, touch (on a touch device), the enter key, or the space bar. If any of those methods does not work, it is a flaw that must be fixed. The button(s) can be scripted to activate any feature of the web site.

### Keyboard

Either the enter key or space bar can be used to activate the button.

### Screen Readers

When the screen reader user tabs to the button, the screen reader will say "button" then read the text within the button element. The button responds appropriately to keyboard commands and acts like an HTML button element.

## Developer and QA Notes

Primary and Secondary buttons should be identified as such to screen-reader users.

The mouse cursor should be an arrow pointer, not a text selector or a hand icon (which would indicate a link).