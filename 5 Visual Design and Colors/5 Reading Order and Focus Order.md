## Reading Order and Focus Order

The Document Object Model (DOM) order determines the reading order and tab/focus order.

This usually corresponds roughly to the visual layout of the page, but not always. 

CSS positioning can alter the visual layout in ways that don't match the DOM order (potentially making the reading and tab order confusing).

Javascript can inject or modify content and put things in unexpected locations, like above the user's current focus. A person using a screen reader has no way to know if the page has been changed by Javascript - there is no obvious reason to navigate backward, except that users know that developers sometimes make this mistake.

## Reading Order

### The reading order MUST be logical and intuitive

Hot Tip: Turn off Stylesheets in your browser to see an approximation of how a screen reader will read your page. Screen Readers ignore CSS.

The good example is of a set of lists on a page. 3 of the lists, numbered 1, 2, and 3 are in columns next to each other. Number 4 is below them, spanning the full width of the page. The source code lays out these lists in a way that they will be read in numbered order.

The bad example is the same set of lists, but arranged randomly in the source code. Absolute positioning is used to make them appear to be where they are in the first example. The screen reader reads them in the order 3, 4, 1, 2

## Focus or Tab Order

### The navigation order of focusable elements MUST be logical and intuitive

This is the same as the rule above but with focusable elements like buttons.

One of the implications of this rule is that visually-hidden items must not be in the tab order.

### `tabindex` of positive values SHOULD NOT be used

Unlike -1 and 0, positive values create a difference between tab order and reading order.

They also remove items from their natural tab order and place them first. In the following example, the links' tab order would be 4, 2, 3, 1.

```html
<ul>
    <li><a href="#">Link 1</a></li>
    <li><a href="#" tabindex="217">Link 2</a></li>
    <li><a href="#" tabindex="9000">Link 3</a></li>
    <li><a href="#" tabindex="83">Link 4</a></li>
</ul>
```