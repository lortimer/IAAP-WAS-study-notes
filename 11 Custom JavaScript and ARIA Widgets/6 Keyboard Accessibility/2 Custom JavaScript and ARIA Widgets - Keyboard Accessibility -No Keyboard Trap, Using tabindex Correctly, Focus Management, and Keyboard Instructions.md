# No Keyboard Trap, Using tabindex Correctly, Focus Management, and Keyboard Instructions

## No Keyboard Trap

All elements must be reachable by a keyboard. A keyboard trap is when this is not possible for a user - they can't tab out of or past an element.

Apparently, Flash objects, especially in Firefox on a Mac, used to cause this. 

## Using `tabindex` Correctly

### Use `tabindex="0"` to make an element tabbable and focusable

You don't normally want to do this because it doesn't make sense to tab focus things that usually can't receive that focus. Use Cases:

- To add keyboard functionality to legacy code with mouse-only JavaScript events.
- To add keyboard functionality to certain kinds of elements in ARIA/JavaScript widgets, such as the tabs in a tab panel (`<li role="tab" tabindex="0">`).
- To force screen readers to read text inside a form or application that might otherwise be skipped. Note: There are usually better ways of ensuring text can be read in these situations, such as using `aria-label`, `aria-labelledby`, or `aria-describedby`, but `tabindex="0"` can sometimes be an acceptable workaround.

### Use `tabindex="-1"` to make an element focusable by JavaScript (but NOT tabbable)

Use Cases:

- To send the focus to a message — such as an error message or confirmation message — to ensure that sighted users see it and that blind users hear it through their screen readers.
- To send the focus to a control in a JavaScript widget, such as to an inactive tab in a tablist. Before receiving the focus, the inactive tab would be set to `<li role="tab" tabindex="-1">`. After receiving focus, you would use JavaScript to change the tabindex value to 0 (`<li role="tab" tabindex="0">`), which would put the active tab in the normal tab flow. The other tabs (all inactive) would all be set to `<li role="tab" tabindex="-1">`.

### Don't use tabindex with positive numbers

We've talked about why several times. It messes with the natural tab flow of the page and is impossible to maintain.

## Focus Management

### Ensure the programmatic focus order matches the visual focus order
### Avoid device-dependent events

Like mouse events. Use device-independent alternatives, like onblur and onfocus

### Ensure all actionable elements can receive focus. Avoid applying events to elements which are typically not able to receive focus unless focus will be managed

Basically, only bind events to natively-focusable elements. If you put events on non-focusable elements, you have to also make them focusable.

### Ensure that simulated controls, simulated dialogs, calendar controls, embedded media content, menus and other actionable dynamic content can be accessed, operated, and closed from the keyboard

### Ensure that focus shifts back to the point where interaction started when the simulated dialog or control is closed

### Ensure that focus changes appropriately when dynamic content changes

- For content added to the screen in reaction to a user-fired event, focus should be shifted to the new content
- For content removed from the screen in reaction to a user-fired event, focus should be shifted to the next logical place in the interaction
- For content changed that is not in reaction to any user-fired event, the user should be notified of the change

### Avoid opening new windows without user notice; Avoid opening new windows based on focus change.

Tell users a link will open in a new window (or tab?) in the body of a link.

Don't open a new window based on non-actions, like hovering over something.

### Provide keyboard interactions to simulated controls which mimic their desktop equivalents

Make non-standard and custom widgets act like their operating system counterparts so people will be familiar with how to operate them.

## Keyboard Instructions

Just because your custom widget is accessible doesn't mean people will know how to use it.

### Users may not expect or be aware of ARIA keyboard patterns

"Tab once to get into the object, and tab again to get out of it", use arrow keys to navigate inside it. Some users are not familiar with this pattern yet.

### Should You use ARIA keyboard patterns?

Some users might think a custom widget is not accessible even when it is because they don't know what buttons they can use to interact with it. Some people argue that we shouldn't use ARIA keboard patterns for this reason.

The course argues that the sooner the web adopts ARIA keyboard patterns, the sooner people will become familiar with them.

### Consider providing brief instructions for keyboard users

For sighted keyboard users and potentially-blind keyboard users. Ways to implement:

- Write the instructions above the widget for everyone to see.
- Make the instructions appear as a pop-up tooltip when the widget receives focus. Use aria-live to announce the text in the tooltip.
- Make the instructions appear as normal text when the widget receives the focus. Consider adding an outline or background color to draw attention to the text for sighted users. Use aria-live to announce the text.
