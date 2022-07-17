# 5 Form Validation

Even with good instructions, we have to validate forms for mistakes to protect the user from entering bad information.

## Error Prevention

### Best Practices

Design forms to avoid errors including the previous lesson. Also:

- Conventional design patterns: The more familiar your users are with the methods you're using in your design, the easier it will be for them to understand what to do. This includes using traditional form inputs as much as possible and using custom widgets only when necessary.
- Visual design that focuses user attention: Ensure labels and instructions are near their respective inputs. Reduce distractions in the visual design. Use visual cues to guide users to fill out the form properly. Make error messages and confirmation messages visually obvious.
- Confirmation prior to submitting: Summarize what will happen when the user submits the form, BEFORE the form is submitted. Ask the user to verify that the information is correct. This is especially important when actions are irreversible.
- Confirmation after submitting: Summarize the result on the screen after the form is submitted, to let users review their action once again.
- Reversible actions: Whenever possible, allow users to reverse actions to restore things to their previous state. In some cases, it may be beneficial to save multiple past actions to allow users to roll back to one of several previous states. Reversible actions can be accomplished through an "undo" feature, through a way to contact customer service, or through some other method to correct mistakes.
- Email confirmation: Where appropriate, send an email confirmation to users as an additional safety check so they can feel confident that the action worked as intended, 

## Design Pattern 1: Error/Success Summary

Provide feedback on form submission with a summary at the top of the page.

### Good Example: Form with Validation Results at the Top

Implementation details of this technique include:

- Set invalid fields to aria-invalid="true"
- Move focus to error/success message
- Ensure error/success message container is set to tabindex="-1". Otherwise, focus cannot be set successfully.
- Provide a count of errors so that users get a sense of the scope of the problem.
- Ensure error messages are associated with form fields using aria-describedby so that screen reader users know how to fix the problem
- Ensure error messages are visible so that sighted users know how to fix the problems
- Ensure error messages are adjacent to the inputs so that screen magnification users can easily see which messages belong to which fields.

If form submission causes a new page to load, or the same page to reload:

- The page title should reflect success or error status
- Provide a quick way to reach the detailed error messages on the screen
  - Skip to main content link
  - Move focus to the confirmation message after the page loads
    - Be careful to let the page load first before trying to focus an element. This gives screen readers time to figure out what is on the page.


## Design Pattern 2: Send Focus to First Error

Instead of showing a message, sending focus to the first field that contains errors is fine. They can then navigate the rest of the fields and find the ones marked as invalid.

Implementation details of this technique include:

- Set invalid fields to aria-invalid="true".
- Move focus to the first field with an error.
- Ensure error messages are associated with form fields using aria-describedby so that screen reader users know how to fix the problem.
- Ensure error messages are visible so that sighted users know how to fix the problems. In this particular example, an error icon is visible at all times, but the error explanation is visible only when the user focuses on the field with an error or hovers the mouse over it. A tooltip message pops up with the error explanation. Advantage: Cleaner interface. Disadvantage: Users will not know how to correct the error at one glance (but they will know after focusing or hovering on the input).
- Ensure error messages are adjacent to the inputs so that screen magnification users can easily see which messages belong to which fields. In this example, the icon is directly to the left of the input. The tooltip appears directly to the right. Positioning the tooltip below the input or near the icon would probably be more effective for screen magnifier users, especially on small screens, but this layout can still be acceptable on full size screens. The styles in this example are set up so that the tooltips appear below the input on screens with smaller resolution, or when users zoom in the browser.

When the page navigates or reloads, the same good practices apply as Design Pattern 1

## Design Pattern 3: Inline (Real-Time) Validation

For screen-reader users, it's acceptable to wait until form submission to understand validation errors. The usability problems with real-time validation are substantial.

Many screen reader users will explore a form before they fill it out, focusing each field in turn. If the form has a lot of validation triggers tied to blur events, the screen reader user could trigger them all before filling out the form. This is annoying for sighted and screen-reader users.

A good example is a password strength indicator that announces (via aria-live) the password quality.

the aria-live announcements are delayed by 2 seconds so the user doesn't hear them with every keystroke. Announcing something with aria-live on blur is a bad idea, because the screen reader also wants to announce the newly-focused element.

## Error Identification Considerations

### Error feedback SHOULD be made available immediately after form submission (or after an equivalent event if there is no form submission event)

If this doesn't happen, the user might assume the form is broken and give up.

### Error feedback SHOULD be programmatically associated with the appropriate element
### Error feedback MUST be programmatically determinable
### Error feedback MUST be meaningful
### Error feedback MUST be visible

## Success Confirmation Considerations

### Success confirmation feedback SHOULD be programmatically determinable
### Success confirmation feedback SHOULD be meaningful
### Success confirmation feedback MUST be visible