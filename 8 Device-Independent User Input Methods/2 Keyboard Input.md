# 2 Keyboard Input

People who do not use a mouse are likely to use a keyboard. A huge variety of input devices also emulate keyboard inputs.

Someone using only a keyboard has to be able to interact with controls, find items and follow visual and programmatic focus.

Programmatic focus is familiar to developers, but visual focus is distinct and important. Sometimes, a visual indicator of focus does not exist or doesn't match programmatic focus, which can be very bad for users.

## Enabling Keyboard Access on a Mac

Strangely, MacOS does not enable keyboard access by default. This means that in Firefox and Safari, you cannot tab to things on a web page. Fixing this requires enabling keyboard accessibility in 2 places:
- System Preferences > Keyboard > Shortcuts (there is a checkbox at the bottom of this screen under "Full Keyboard Access")
- Safari Preferences

Google Chrome enables keyboard access for itself by default.

**If you don't enable keyboard access, your automated accessibility tests will not work correctly!**

## Tab Focusability

### Links, buttons, and interactive controls MUST be keyboard-focusable

If they don't, keyboard users straight-up can't interact with them.

Custom controls like a `<span role="link">...</span>` won't automatically be focusable, and need `tabindex=0`

## Tab Order

As discussed in the "Semantic Structure and Navigation" course.

### The navigation order of focusable elements MUST be logical and intuitive

### `tabindex` of positive values SHOULD NOT be used

## Visual Focus Indicator

### All focusable elements MUST have a visual focus indicator when in focus

The default is sufficient but can be improved upon, especially to make the colors stand out in your design.

### Focusable elements SHOULD have enhanced visual focus indicator styles.

### The contrast of all visual focus indicators against the background MUST be at least 3 to 1

### Visual Focus Indicator and High Contrast Mode

It is best practice to include a border as part of the focus indicator style, because High-Contrast mode can cancel out background color changes. Also, don't indicate focus with only color because some people have different color perception.

## Keyboard Functionality

### Functionality MUST be available using the keyboard, unless the functionality cannot be accomplished in any known way using a keyboard

An example of the exception would be free-hand drawing, but if you're making a web app to allow free-hand drawing, you're kind of a coward not to make a keyboard scheme that allows the same experience.

Just use standard HTML controls and you don't have to worry about keyboard operability.

## Keyboard Traps

### Keyboard focus MUST NOT be locked or trapped in a particular page element and the user MUST be able to navigate to and from all navigable page elements using only a keyboard

Basically, you have to make sure the tab key can move through all the elements on the page, beginning to end. If you have a trap section, you have to provide instructions on how to exit it with a keyboard command.

Modals and dialogs that cover the screen should trap focus, so long as they have a keyboard operable way to close them and return to the main content.

## Focus Management During Interactions

### The focus MUST be purposely moved or set (via JavaScript) onto the appropriate element when the user's action requires a change of context or location for effective keyboard or touch interaction

When content or controls are added to the screen in response to a user firing an event, their focus should be moved to the new content or control. When they are done with this interaction, their focus should be moved back to where they left off.

When content or controls are removed from the screen, the user's focus should be shifted to the next logical place on the page.

#### Good Example

When the user opens a modal dialog, their focus is shifted to the first element on the dialog.

#### Bad example

The user triggers a dialog to open but their focus is left behind, so they don't know a dialog opened.

### The focus MUST NOT become lost or reset to the top of the page, except when loading or re-loading a page

If the focus is not managed when changes happen on the page, the user's focus may become lost, effectively returning it to the top of the page. This is very confusing and frustrating. At best, they have to tab their way back to where they left off. At worst, they may wonder if they ended up on a different page.

### When moving or setting focus, the destination element MUST contain programmatically determinable text

There's no point in focusing an element with no text in it. Nothing is read, so it's as if you didn't move the focus. The text in the newly-focused element is key to helping the user understand what changed.

## The ARIA Keyboard Interaction Model

The web traditionally hasn't used more than just the tab and enter keys, where operating systems have created full-featured keyboard schemes. ARIA includes keyboard interaction patters that expand HTML's keyboard functionality. The [WAI Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/) provides recommendations for keyboard interaction patterns for common widgets.

### Tab to the Widget; Use Arrow Keys Within It

Generally, these recommendations boil down to tabbing to a complex control, then using arrow keys to navigate within it. That way, tab lets the user leave the whole widget with a single keystroke instead of having to tab through many controls.

## Keyboard Shortcuts

### Page-specified shortcut keys and accesskeys MUST NOT conflict with existing keyboard shortcuts in the browser, operating system, or assistive technologies

Screen readers and operating systems will override these shortcuts, rendering them unavailable.

To me, this means specifying keyboard shortcuts is a bad idea in general because the user can specify whatever shortcuts they want with the browser, OS, and screen reader. You can't predict it. If you need to have them, they should not be required for functionality, and they should be customizable.

## Giving Users Keyboard Instructions

### When custom keyboard behavior is required to use a component, keyboard instructions MUST be provided

Keep in mind both sighted keyboard users and blind screen-reader users.

Ways to provide instructions:

- Write the instructions above the widget for everyone to see.
- Make the instructions appear as a pop-up tooltip when the widget receives focus. Use aria-live to announce the text in the tooltip for screen readers.
- Make the instructions appear as normal text when the widget receives the focus. Consider adding an outline or background color to draw attention to the text for sighted users. Use aria-live to announce the text for screen readers.

### ARIA widgets that require more than just the Tab key to interact with may be confusing to users, so you MAY provide keyboard instructions

New widgets always require orientation, so consider providing instructions if your widget is new to people in some way.