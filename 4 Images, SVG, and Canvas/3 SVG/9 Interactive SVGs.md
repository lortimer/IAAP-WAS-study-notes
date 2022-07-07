# Interactive SVGs

## Interactive `<svg>` objects MUST be fully keyboard-accessible

This includes but is not limited to basically all of WCAG 2.1:

- All links, buttons and controls must be keyboard-focusable and usable by keyboard users.
- All focusable elements must have a visible focus indicator.
- The scripting must manage the focus when activating, deactivating, and/or dismissing features (like dialogs, menus, etc.); the focus must be sent to the proper place at the proper time.
- The `<svg>` object must not trap the keyboard focus.
- The tab order (or arrow key order, if appropriate) must be logical.
- All focusable elements must be visible on the screen (or become visible once focus lands on them).

## Interactive `<svg>` objects MUST be fully touchscreen-accessible

This includes:

- All mouse-only actions have a touch equivalent action.
- All keyboard-only actions have a touch equivalent action.
- All gesture-dependent actions have an equivalent non-gesture method to achieve the same result (this rule exists because screen readers override and disable page-specific gestures in most cases; a click action is best for touchscreens).

## Interactive `<svg>` objects MUST communicate the applicable name, role, and value of controls, events, and semantic elements within the `<svg>` object

An interactive SVG is basically a custom ARIA widget. You better be prepared to test the heck out of it if you're going to use this technique.