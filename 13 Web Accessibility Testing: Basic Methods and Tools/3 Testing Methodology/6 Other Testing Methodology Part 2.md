# Other Testing Methodology Part 2

## Landmark Testing

Landmarks help fulfill the WCAG Requirement that there is a mechanism for users to allow them to skip over repetitive content.

Some basic best practices for using landmarks:

- Make sure that there is only one instance of `<header>`/`role="banner"`, `<footer>`/`role="contentinfo"`, and `<main>`/`role="main"` on the web page.
- If there are multiple instances of `<nav>`/`role="navigation"`, the sections should have unique names provided through aria-label or aria-labelledby (these unique names will be conveyed through a screen reader).
- The number of landmarks on a web page should be relatively low and appropriate for the content on the web page. For instance, if there are too many navigation landmarks, users may have a hard time figuring out the purpose of all those landmarks.

### Testing Methodology for Landmarks

The easiest way to test these is manually with a screen reader. Mobile screen readers define landmarks differently than HTML. On a page that has a header with a nav in it, then a main with a list in it, Talkback will only let you navigate to 3 of those.

1. First, it highlights the header and calls it "section"
2. Then, it highlights the nav and reads "navigation, section" reading both the nav and the header.
3. Finally, it will focus on the list and say "list". No mention of the main whatsoever.

You can use the screen reader to navigate by landmarks and generate a list of landmarks when testing.

## Test for Headings

Tests should look for 

- Headings are used: The page has a heading. In almost all pages there should be at least one heading, usually at the beginning of the main content, after the navigation.
- Real headings: Make sure headings use real heading markup (`<h1>, <h2>, <h3>, <h4>, <h5>, <h6>`), and not just visual styling that looks like headings.
- No misuse of headings: All text that is marked up as a heading is really a conceptual section heading. If the text isn't really serving the purpose of a heading, it shouldn't be marked as a heading.
- Heading hierarchy: The heading hierarchy is meaningful. Ideally the page starts with an "h1" — which is usually the same as or similar to the page title — and does not skip levels; however, these are not absolute requirements.

Like with Landmarks, you can navigate by headings and generate a list of headings while testing.

## Test Link Text Quality

Links need to make sense out of context since people don't always hear the surrounding text when reading them. They should describe where they go. Below is a table describing common types of links and how to make sure they are accessible.

| Link Type                | Considerations                                                                                                                                                                                                                                                                                                                                                                            |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Link Text by Itself      | For link text that is by itself or stands alone on its own, the text should describe the purpose of the link or provide some indication of the content of the target page.                                                                                                                                                                                                                |
 | Link Text within Context | The link itself combined with its enclosing text should describe the purpose of the link.                                                                                                                                                                                                                                                                                                 |
 | Images as Links          | If a link contains only an image, the image's alternative text should describe the purpose of the link. If the image is paired with text inside the `<a>` element, and the text adequately describes the purpose of the link, then the image should be ignored by assistive technologies by using an empty, or null, alt attribute (alt="") or by rendering it as a CSS background image. |
 | Icons as Links           | For icon fonts used as links, the purpose of the link should be conveyed using one of the following ARIA attributes: aria-label, aria-labelledby, or aria-describedby. The id references used for aria-labelledby and aria-describedby should properly describe the link.                                                                                                                 |

It's best to test links by navigating to them and evaluating them, or generative a list of them.

## Test Form Labels and Instructions

Forms can be a single text field like search, or a complet form with many input types and labels.

### Testing Methodology for Form Labels

#### Individual Form Elements

1. The label for the form element is visible to sighted users and near its form element.
2. Placeholders alone aren't used as labels. Since placeholders disappear once a user enters information, placeholders are not sufficient as visible labels.
3. The label is exposed to assistive technologies. To check for this, use a screen reader and place the focus on the form input (text field, radio button, etc.). The label associated with the form input should be rendered by the screen reader. If not, the label is not marked up properly.
4. The label properly names or conveys the purpose of the form element. Users should know what to do when they encounter the label.
5. When an image or icon is used as a label, check for a proper text alternative using a screen reader. The text alternative should be rendered when focus is placed on the form input.

#### Grouped Form Elements

1. A group label for related form elements is visible to sighted users and near the form elements it labels.
2. The group label is exposed to assistive technologies. Use a screen reader and place the focus within the form grouping. When focus is placed on the first form element in the group, both the group label and the individual label for the form element should be rendered by the screen reader. If the group label isn't rendered, then it is not properly marked up.
3. The group label properly names or conveys the purpose of the form grouping.


### Testing Methodology for Form Instructions

#### Entire Form and Grouped Sections of Form

1. The instructions for the form or form group are visible and appear before users interact with form elements.
2. The instructions are available to assistive technologies (Check that a screen reader renders instructions to users).
3. Instructions for form groups are associated programmatically with their specific form elements.
    1. To check this, use a screen reader and tab into the form grouping. The screen reader should render instructions to users either when they tab into the grouping (`<legend>`) or when they tab to a form element in the grouping (aria-describedby).
4. The instructions are meaningful and actionable. Users should know exactly what to do after reading the instructions.
5. Instructions do not rely on sensory characteristics like color alone. For example, instructions should not say fields outlined in red are required.


#### Individual Form Elements

Individual inputs may have specific instructions.

1. Check that instructions are visible and near the form element they describe.
2. Check that instructions are available to assistive technology users. Use a screen reader and place focus on the form element. The screen reader should render instructions to users when focus is placed on the form element.
3. Make sure instructions are specific and meaningful. Users should know whether a field is required or what kind of formatting is needed to complete the form field.
4. Make sure instructions do not rely on sensory characteristics such as using color alone to convey a required field.

## Test Form Validation

### Error Messages

Feedback for errors is provided immediately. The users need to know what the error is and where it is. There are many strategies for doing this - summaries with each error and a link, errors with each field.

#### To Test Error Messages 

1. Locate a form on the web page.
2. Do not fully complete the form, especially fields that are required or require special formatting (make mistakes on purpose).
3. Submit the form.
4. Check that feedback regarding errors is provided immediately after submission, this may include:
    1. An error summary
    2. Error messages for specific form elements that are next to the form elements
5. Make sure that error messages are informative and actionable (users should know what to do to fix the error).

#### To test with a screen reader

1. Repeat Steps 1 through 3 above using a screen reader.
2. Check that feedback is rendered by the screen reader immediately after submission.
    1. A global error summary may be provided
    2. Note: It is a best practice to ensure a method is provided to quickly access errors in the form in the error summary (e.g., a link to go to the first error in the form)
    3. Or focus may be shifted to first form element with an error
3. Navigate to all the form elements with specific errors and make sure the error messages for those particular form elements are conveyed through the screen reader.


###  Success Messages

#### To test success messages

1. Locate a form on the web page.
2. Complete the form based on the instructions, if provided (see Test Form Labels and Instructions to evaluate the quality of instructions).
3. Submit the form.
4. Check that a success message is provided immediately after submission. The success message should be visible and have meaning (e.g., "Your form has been successfully submitted.").

#### To test with a screen reader

1. Repeat Steps 1 through 3 using a screen reader.
2. Check that the screen reader conveys the message immediately after form submission.

#### To test with mobile screen readers

Ensure that success and failure messages are visible and exposed to mobile screen readers.

## Testing Custom Widgets

This is a whole subject on its own, and requires real user testing more than most subjects because it's really about creating a good user experience.

Screen readers need to be able to figure out the name, roles, and state or value of each part of the custom widget. Using standard HTML elements inside your widget helps.

### Testing Methodology for Keyboard Accessibility and Custom Widgets

Developers usually have to program the keyboard functionality from scratch, so you have to test widgets with the following in mind.

The ARIA keyboard design patterns can help build good widgets AND test them: https://www.w3.org/TR/wai-aria-practices-1.1/#aria_ex

- Controls must be focusable.
- The tab order must be logical and intuitive.
- Custom keystrokes must not conflict with common screen reader and browser keystrokes.
- Focus must be visible at all times.
- Focus must be managed throughout interactions.
- Content must not cause a keyboard trap.

### Testing Methodology for Keyboard Accessibility and Screen Readers

Users need to be able to determine:

- The name or label of the custom widget or element. For instance, if users interact with a modal dialog, they need to know what the modal dialog is presenting to them (e.g., "Confirm Preferences").
- The role of the custom widget or element. Users need to know what type of element they're interacting with. Using the same modal dialog example, it should be conveyed to users through their assistive technology that they are interacting with a dialog.
- The state of the custom widget or element. If the state of the user interface component changes due to a user's interaction or response to it, assistive technologies need to convey the changes. A good example is an expandable region. If the user expands the region, it needs to be communicated through the assistive technology that the region is expanded.
- The properties associated with the custom widget or element. If there are attributes that contribute to the users understanding of interacting with the widget or element, these properties must be conveyed. For a slider, there is a minimum value and a maximum value that must be conveyed to users to properly interact with it.
- The value of the custom widget or element. Using the slider example again, when a user selects a value between the range provided in the slider, the value they select must be conveyed to them.

When evaluating custom widgets, fall back on testing as a user:

- Go through all of the content on the web page relying only on a screen reader and keyboard.
- Interact with all user interface components.
- Check that the information conveyed through the screen reader accurately conveys what is displayed as you interact with the components.
- Make sure that the information is reliable and that the components are compatible with the screen reader.

