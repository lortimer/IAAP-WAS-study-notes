# Value

"Value" here refers to properties and states that can apply to elements that give the reader information about them.

These properties and states are just the current value of the element, and must be updated manually as the states change. For example, if an element has `aria-expanded="false"`, when clicked, the Javascript must set this value to true.

This page listed some of the states and properties, but didn't go into detail about them. See level-2 headings below for the lists. Before that, I'm going to read [the official documentation](https://www.w3.org/TR/wai-aria/#introstates) on this concept and take notes here.

## WAI-ARIA States and Properties

Changes in states or properties is supposed to notify the user, similar to a live region.

### Managed States

Some accessibility states called "managed states" are controlled by the user agent. Examples include keyboard focus and selection. They often have corresponding CSS pseudo-classes like :focus and ::selection. We are not talking about managed states here.

### Unmanaged States

Controlled by the author of the document. Most modern user agents support [CSS attribute selectors](https://www.w3.org/TR/css3-selectors/#attribute-selectors), which allows the author to change the UI based on ARIA attribute information instead of using JavaScript.

In the following example, CSS changes the font weight and image source for a checked checkbox:

```css
[aria-checked="true"] { font-weight: bold; }
[aria-checked="true"]::before { background-image: url(checked.gif); }
```

## Global Values

These properties and states can be applied to any element on the page, even without an aria-role.

- Properties
    - aria-atomic
    - aria-controls
    - aria-describedby
    - aria-dropeffect
    - aria-flowto
    - aria-haspopup
    - aria-label
    - aria-labelledby
    - aria-live
    - aria-owns
    - aria-relevant
- States
    - aria-busy
    - aria-disabled
    - aria-grabbed
    - aria-hidden
    - aria-invalid

## Widgets

These properties and states apply to user interface objects like alert, alertdialog, menu, progressbar, tooltip, and other widgets. (Do they mean "application regions"?)

Global ones excluded.

- Properties
    - aria-autocomplete
    - aria-level
    - aria-multiline
    - aria-multiselectable
    - aria-orientation
    - aria-readonly
    - aria-required
    - aria-sort
    - aria-valuemax
    - aria-valuemin
    - aria-valuenow
    - aria-valuetext
- States
    - aria-checked
    - aria-expanded
    - aria-pressed
    - aria-selected


## Drag and Drop

- Properties
    - aria-dropeffect
- States
    - aria-grabbed


## Live Regions

- Properties
    - aria-atomic
    - aria-live
    - aria-relevant
- States
    - aria-busy
