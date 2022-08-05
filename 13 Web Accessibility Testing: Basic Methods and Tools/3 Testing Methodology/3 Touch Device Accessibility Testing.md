# Touch Device Accessibility Testing

## Touch Target Size

This is anything you can click to activate it with your finger.

Touch targets have to be 9.6mm square minimum, which is equivalent to 44 CSS pixels.

### Testing Methodology for Touch Target Size

- Responsive Design: (Desktop) If the web page is responsive, shrink the viewport of the browser down to appropriate mobile sizing (tablet and phone).
- Forms: When HTML labels are used in forms, users should be able to select the label itself to place focus on or in the form element. Test to see if the label can be selected. This is especially important for radio buttons and checkboxes as they are small in nature.
- Links (by themselves) and Buttons: Ideally, the padding around links and buttons should also be a part of the target, not just text inside. Test to see if the padding around these elements can be selected. Using only the text inside the padding makes for a smaller target.
- Links inline with text: Links that are surrounded by regular text should have enough characters to make them 9.6mm. Extra padding for height may break visual layout, so it is critical that they are wide enough to trigger.


## Touch Functionality

Same as with a keyboard, you have to be able to do all the functionality with a touch. This is rarely an issue because touches emulate mouse clicks.

## Touch Functionality with Screen Reader On

Screen readers on touch devices override the standard gestures on the device. This is the same as above, but with the screen reader on.

- Touch functionality is available when the screen reader is on, including activating links, buttons, and interacting with custom widgets.
- Custom gestures aren't the only means to interact with content on a web page. If a gesture can be used to interact with content, a touch-based alternative is provided (e.g., being able to select/click on left and right arrows as opposed to swiping left or right to view content).
