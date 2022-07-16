# Mouse Input

Most developers consider mouse input because they use a mouse themselves. They often fail to consider things like:
- Using a mouse with reduced precision because of a motor disability,
- Using a mouse with low vision and needed to be able to tell where your cursor is and what it is touching.

## Click Target Size

### The click target size SHOULD be large enough to facilitate easy use with a mouse (including for users with tremors or limited dexterity) without risking activating an adjacent link or button

Good Example: Explanding the click target size of a superscript, numeric link by adding brackets around the number. 

## Visual Hover Indicator

### The mouse cursor icon on hover SHOULD correspond to the type of action allowed by the element

Links turn the cursor to a pointer, **buttons don't**. This is because buttons and other clickables typically have strong affordance - it is obvious that they are clickable by how they look. Links have weak affordance, they are simply underlined text.

### An enhanced visual hover indicator SHOULD be provided

The example provided is a link that gets a light-yellow background and a blue border when hovered.

The bad example is a button where the text changes from gray to white on hover. It's too subtle.

### The mouse cursor icon on hover SHOULD correspond to the type of action allowed by the element.

## Pointer Cancellation

### For functionality that can be operated using a single-pointer, at least one of the following MUST be true: no down-event, can abort/undo, up reversal, or essential

The following allow people to undo an accidental click or tap:

- No Down Event: The down event of the pointer is not used to execute a function, meaning if you press your mouse button on an element, it doesn't do its action until you release your mouse button on it also.
- Abort or Undo: Completion of a function is on the up event AND a mechanism is available to abort the function before completion, or undo it after.
- Up Reversal: The up event reverses the outcome of the preceding down event
- Essential: Completing the function on the down event is essential.

The preferred method is to make action occur on the up event. This allows the user to slide their mouse or finger away before releasing. Better is to use the `onclick` event. This makes the action take place on the up event, **but only if the preceding down event happened on the same element**

An example of essential down event is an on-screen piano or an on-screen keyboard.