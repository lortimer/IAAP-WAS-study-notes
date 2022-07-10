# Keyboard Accessibility

If you really hate your end user and don't value your time, you can theoretically make UI elements using `canvas` and handle clicks and other inputs with Javascript.

If you do this, your element has to have or handle:
- Mouse events and equivalent keyboard events.
- Visible hover and keyboard focus style
- An accessible name and role, most easily done with `role` and `aria-label`.

You can put a real button inside the canvas to get some of that for free, but it doesn't get all of it.

## A `<canvas>` element operable with mouse MUST be keyboard accessible

Including:
- Keyboard focusability
- Keyboard operability, preferrably with standard buttons like Enter and Spacebar