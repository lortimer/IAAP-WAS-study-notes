# Button (Toggle)

A toggle button is similar to a checkbox because it is either selected or not selected, and every toggle button can operate independent of all other toggle buttons. In fact, a checkbox can be an acceptable alternative to a toggle button.

## Expected Operation

### Keyboard

Either the enter key or space bar can be used to mark the button as pressed or not pressed.

### Screen Readers

When the screen reader user tabs to the button, the screen reader will say "toggle button," read the text within the button element, and will communicate the button's toggle state. The exact wording varies from one screen reader to the next. It could say "on" or "off" (Narrator), or "pressed" or "not pressed" (NVDA), or similar. It uses `aria-pressed` for this.

## Key Accessibility Features

- The ARIA buttons are designed to give an identical experience to standard HTML buttons.
- The attribute `aria-pressed` is set to true or false, to indicate the current state.

## Developer and QA Notes

The toggled state must be visually distinguishable from the untoggled state using more than just color. The implementation here includes an icon.

## Browser and screen reader support

- VoiceOver + Safari iOS: 	Standard button does not read aria-pressed state correctly. Bug in iOS where it won't work unless role="button" is present.
- VoiceOver + Safari MacOS: 	Not supported. The state change is not spoken.
- Narrator + Edge: 	Not supported. The state change is not spoken.