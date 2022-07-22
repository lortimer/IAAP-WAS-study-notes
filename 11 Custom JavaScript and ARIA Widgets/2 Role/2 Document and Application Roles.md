# Document and Application Roles

## The Document Role

The DOM automatically has this role, there is no need to apply it to the body or anything. It allows users to navigate non-focusable elements with their screen reader.

The only reason to use this role is to enable screen-reader navigation inside another kind of region, like an application region. The `dialog` role is a kind of application role, so if you put text in a dialog, it may not be accessible without
`role="document"`.

## The Application Role

This role exists to give developers complete freedom over programming the behaviors of a widget, including keyboard event handlers. Using this role, or a sub role, requires thoughtful planning.

### The application role MUST NOT be used anywhere where screen reader users need to use page navigation features

The application role turns off a screen reader's ability to navigate the structure of the document. It turns off basically all of the shortcut keys. The only ones it doesn't turn off are:

- The Tab key to go through focusable items, such as links, form elements, and anything with tabindex="0".
- The Enter or Return key to activate a link or button, or to submit a form.
- The space bar to activate a button or submit a form.
- The arrow keys to choose elements within <select> lists or to choose between radio buttons

### The document role SHOULD be used inside an application region if part of an application region requires screen reader users to navigate text content

Thus, if there is text inside your application region, as in a dialog, you need to wrap the text content with a container that has `role="document"`

### Meaningful non-focusable content in an application region MUST be programmatically associated with focusable elements, or MUST be made accessible to screen readers in some other way

The following will not be visible in an application region without `role="document"` or `tabindex=0`:

- paragraphs
- headings
- `<div>` elements
- `<span>` elements
- lists
- tables

### Non-focusable items SHOULD NOT be made focusable just for the sake of making them readable to screen readers

So you might think, just add `tabindex=0` to everything in an application region. This does not make them interactable in the normal way. They can't read them one line, word, or letter at a time, or do any of the normal text-based stuff they normally can do. The can only focus the element and hear it in its entirety. They can't event pause effectively.

It's also not normal to be able to tab to a non-focusable element, so it's confusing.

### The application role MUST NOT be used anywhere except around a widget that requires it

Never wrap a whole page with `role="application"`. Wrap it around only as much as you need to.

### Some roles automatically invoke application mode

Including:

- `role="dialog"`
- `role="alertdialog"`
- `role="tablist"`

Focus must be managed inside these roles, or they must have an inner container set to `role="document"` 
