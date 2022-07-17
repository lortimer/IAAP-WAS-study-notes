# Dynamic Forms & Custom Widgets

## Progressive Form Updates

Maybe you have a form where information in one step affects the options available in later steps. 

### Best Practices

- Change future options, not past ones. Screen reader users are unlikely to go back unless they know there is a reason to do so. Dynamic changes should happen further down the DOM
- Allow users to change their past choices. Provide an easy way to do that. One example I can think of is with a paged form that exposes buttons to jump to each page.
- Consider limiting access to one step at a time. Having multiple steps on the screen can be overwhelming. Sometimes, it's okay to leave past options or a summary of them visible and reveal new sections as the user goes along.
- Help the user understand how many steps there are and how many they have completed.
- Manage keyboard focus, especially when things change dynamically. Pay attention to forward and backward paths.
- Consider providing a concise summary of the choices made throughout the forms. It can be difficult to navigate back through all the choices. You can summarize or describe the choices made in this step or previous steps. Programmatically associating this with the submit button is a good idea.

### Good Example
https://dequeuniversity.com/assets/html/module-forms/progressive/good/index.html

## Changes in Context

It can be confusing if a user action unexpectedly causes a change of context, which could be a change to:

- The user agent: when links cause the user to leave the browser for a different application
- The viewport: when a new window opens, the screen scrolls, or elements change places
- The focus: when focus is moved to another element
- The content: when the meaning or the page changes or elements are rearranged.

These aren't inherently bad, but hurt accessibility when the happen automatically without the user requesting the change. The user should be able to intentionally take a strong action like clicking a button to change context.

### Focusing on an element MUST NOT automatically trigger a change of context, unless the user has been adequately advised ahead of time

A bad example is when focusing a form field opens a dialog

### Changing an element's value MUST NOT automatically trigger a change of context, unless the user is adequately advised ahead of time

The good example is changes occuring when the user clicks "Submit"

The bad example is a `<select>` element that triggers navigation to a different page when one of the options is selected. This happens with unexpected inputs for keyboard users, like when they press the down arrow to visit the next option.

#### Bad Example: Shifting Focus Automatically to the Next Field

I usually find this feature convenient, myself. If a user isn't notified that this will happen, they may accidentally enter incorrect information. Conisder the keystrokes necessary to enter a social security number into 3 inputs that don't do this. It would be something like `tab 999 tab 99 tab 9999`. If focus moved from one field to the other, you have entered an SSN that looks like `999-XX-99XX and unexpectedly moved yourself out of the field.

I think it's OK to use this technique if you warn the user that it will happen, and especially if you allow them to opt into it site-wide. In case of multi-input values, it may be better to combine them into a single field.

### Hovering over an element with the mouse MUST NOT automatically trigger a change of context, unless the user has been adequately advised ahead of time

#### Bad Example: Dialog triggered by hover

https://dequeuniversity.com/assets/html/module-forms/context/bad/hover/index.html

## Custom Form Inputs

### Native HTML form elements SHOULD be used whenever possible

### Custom form elements SHOULD act like native HTML form elements, to the extent possible

Model custom inputs after native ones, including keyboard interaction. If your new input is innovative, still look to native ones as models.

### Custom form elements SHOULD have appropriate names, roles, and values

Values include required, expanded, input value, selected, etc.

### Updates and state changes that cannot be communicated through HTML or ARIA methods SHOULD be communicated via ARIA live messages