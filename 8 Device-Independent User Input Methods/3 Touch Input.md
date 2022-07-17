# Touch Input

Touch functionality wasn't well understood when WCAG 2.0 was written in 2008, but WCAG 2.1, from 2018, has recommendations

## Touch Functionality

### Functionality SHOULD be available using standard touch methods, unless the functionality cannot be accomplished in any known way using a touch device

#### Keyboard vs. Click Events

Touch devices rely on click events by turning taps into clicks. Mouse clickability makes the element tappable as well.

#### Drag and Drop events

Some touch devices support drag and drop, but others don't. Even when they do, drag and drop is fragile and unreliable. Drag and drop should be an optional enhancement to the main functionality.

#### Scripted Gestures

Same as drag and drop. Gestures may or may not work on a given device, and some are reserved by the operating system, like pinch to zoom.

## Touch Functionality with Screen Reader Turned On

### Functionality SHOULD be available using screen reader touch methods (e.g. click actions), unless the functionality cannot be accomplished in any known way using a touch device

Screen readers on touch devices typically disable scripted gestures and implement their own. Swiping left and right navigate through elements, tapping focuses an element, and double tapping activates the focused element. A web page that relies on gestures will not receive them with the screen reader turned on.

#### Good Example

If a page has a set of images, you may be able to swipe left and right on the main image to see other images. The good example would also provide buttons to click on to see other images.

## Touch Target Size

### The click/touch target size SHOULD be large enough to facilitate easy use with a finger, without risking activating an adjacent link or button

This especially helps users with motor and dexterity disabilities.

As mentioned before, targets should be 44-48px on standard screens and 88-96px on retina screens. That means 44 CSS pixels on a web page will 

## Focus Trap

### Touch/gesture focus SHOULD NOT be locked or trapped in a particular page element and the user SHOULD be able to navigate to and from all navigable page elements using standard touch actions or gestures

Mobile screen readers use a swipe to navigate from one element to another, so the focus can get trapped just the same as with a keyboard. Keyboard accessibility generally translates to mobile screen reader accessibility

There are a few special cases, though:

#### `onblur` and `onfocus`

Scripts that depend on these events may not work with a mobile screen reader because the screen reader's focus is not always the same as the keyboard's programmatic focus.

#### `aria-hidden="true"`

If this is set on visual elements on the screen, it can cause mobile screen reader focus to be trapped or lost.

#### Off-screen styles

As we've seen in Treble, the technique of hiding elements off screen until they are focused doesn't work on mobile screen readers.

## Pointer Gestures

### All functionality that uses multipoint or path-based gestures for operation MUST be operable with a single pointer without a path-based gesture, unless a multipoint or path-based gesture is essential

Not everyone can perform "multipoint" gestures, like pinch-to-zoom, and "path-based" gestures, like swiping in a particular direction. More accessible means include:

- Single-click, double-click, and click-and-hold
- Single-tap, double-tap, and long press

Essential gestures include drawing a signature on a touch screen where typing your signature is not possible.
