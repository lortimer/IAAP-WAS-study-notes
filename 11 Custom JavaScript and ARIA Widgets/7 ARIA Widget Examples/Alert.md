# Alert

An alert is a special type of ARIA live region. Screen readers will announce the text inside the alert, without moving the focus to the alert message. Alerts are usually styled to visually stand out from the rest of the content, to make them obvious when they appear.

## Expected Operation

### Activation

An alert can be activated by a user action (such as clicking on a button), a timed event, or other circumstance.

### Keyboard

The focus stays where it is. The focus does not move anywhere when an alert is activated.

### Screen Readers

An alert is a special kind of assertive ARIA live region, so screen readers should immediately interrupt anything they were previously saying and instead read the announcement. Most screen readers say "Alert," before reading the text inside the alert.

## Key Accessibility Features

- An empty container is marked as role="alert".
- Text is injected into the container in response to a trigger event.
- Screen readers announce the text.

## Developer and QA Notes 

- The alert appears near the user's focus so even people who magnify the screen will see it.
- The alert is distinct from surrounding text.
- Other alerts are deactivated when one appears.

### Alert versus Alert Dialog

An alert (`role="alert"`) does not require a user action. It does not move the keyboard focus. No part of the page is hidden or obscured or made unavailable at any time.

An alert dialog (`role="alertdialog"`) requires a user action. It acts like a regular dialog, but it is supposed to convey more of a sense of urgency. Screen readers typically say "Alert dialog" when an alert dialog pops up. The focus moves to the dialog and the user is required to take action. Usually this means clicking a button, even if it may just be an "OK" button or a "Close" button. The user cannot navigate out of the dialog with the tab key, and screen reader users cannot use keyboard shortcuts to access semantic elements (headings, landmarks, form elements, etc.) outside of the dialog.