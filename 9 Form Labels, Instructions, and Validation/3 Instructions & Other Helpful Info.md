# Instructions & Other Helpful Info

Helping users avoid mistakes before they happen is more effective than helping users correct mistakes.

## Instructions for Forms, Groups, and Sections

### Instructions for groups or sections SHOULD be programmatically associated with the group

I think the course also applies this rule to whole forms, which it considers to have 1 section? There seems to be no form-level instruction information.

Putting text in the middle of a form is risky. Screen reader users may be in form mode, skipping only to focusable elements and not seeing any text. Associating text with a group label or input makes it visible to them.

There's no natural way to create a _description_ that is associated with a group. `aria-describedby` with `fieldset` and `legend` don't work.

- Option 1: Add instructions to the `legend` as long as they are short. E.G. "Name (Required)"
- Option 2: Associate some instructions with one of the fields, usually the first in the group, with `aria-describedby`.
- Option 3: Put instructions before the start of the form as regular text not associated with anything. This puts the burden on the user to notice and read the text, which isn't ideal because if they enter form mode on their screen reader, they may not notice the text.

#### Good Example: `aria-describedby`

```html
<legend>Create Account</legend>
<p id="mustmatch">Password fields must match</p>
<p><label for="password">Password: </label>
    <input type="password" id="password" aria-describedby="mustmatch"></p>
<p><label for="password2">Re-enter password: </label>
    <input type="password" id="password2"></p>
</fieldset>
```

#### Good Example: Instructions associated with multiple form fields

In this example, the phrase "must not contain spaces" is associated with both the username and password fields. Note that the full instructions ("Username and password must not contain spaces") were not associated with each field, because that would have been too redundant.

```html
<fieldset>
<legend>Create Account</legend>
  <p><strong>Username and password
  <span id="mustnot">must not contain spaces</span></strong></p>
  <p><label for="username">Username:</label> 
    <input type="text" id="username" aria-describedby="mustnot"></p>
  <p><label for="password">Password:</label> 
    <input type="password" id="password" aria-describedby="mustnot"></p>
</fieldset>
```

### Instructions for groups or sections MUST be programmatically determinable.
### Instructions for groups or sections MUST be meaningful
### Instructions for groups or sections MUST be visible
### Instructions for groups or sections SHOULD be visually adjacent to the grouped elements
### Instructions for groups or sections SHOULD be adjacent in the DOM to the grouped elements
### If the instructions are not critical to understand the purpose of a group or section, the instructions MAY be hidden until the user requests them
### Instructions for groups or sections MUST NOT rely solely on references to sensory characteristics

## Instructions for Inputs

### Instructions for an element MUST be programmatically associated with the element

use `aria-describedby` for lenghtier instructions beyond the label

### Instructions for an element MUST be available as programmatically determinable text
### Instructions for an element MUST be meaningful
### Instructions for an element MUST be visible
### Instructions for an element SHOULD be visually adjacent to the element.
### Instructions for an element SHOULD be adjacent in the DOM to the element
### If the instructions for an element are not critical, the instructions MAY be hidden until the user requests them

An example of this would be to put a button adjacent to the field that when clicked shows text describing valid entries for that field. The button should come before the input so people who use screen readers know the extra help is available.

### Instructions for an element MUST NOT rely solely on references to sensory characteristics

## Required Fields

Clearly identifying required fields helps prevent user frustration.

### Required fields SHOULD be programmatically designated as such

`aria-required="true"` is an unambiguous way to designate a field as required. It is invisible, so it needs to be supplemented.

HTML5 `required`: HTML5 has an attribute called `required` you can apply to an input. It is invisible and behaves like `aria-required`, but in some browsers, it also prevents the user from submitting the form with an empty value. It doesn't work in all browsers, so you need to handle errors yourself anyway.

According to Mozilla, if the label already contains the word "required", aria-required should not be added to that input. https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-required#examples

### Required fields SHOULD have a visual indicator that the field is required

Ways to do this include:
- Text instruction before the form saying "fields with an asterisk(*) are required", then putting an asterisk in the label of required fields
  - Downside is that screen-reader users hear redundant "input name star required"
- The same as above but using a font icon instead of the asterisk
  - Screen reader users don't hear the "star" but may be confused because the form instructions mentioned asterisks
- Designate required fields with "(required)" in the label.
  - Redundant for screen reader users, but oh well.
 
### The form validation process MUST include an error message explaining that a field is required if the field isn't identified as required both visually and programmatically in the form's initial state

It's super important that error messages are associated programmatically with the fields they relate to, and visually using more than just color.

When a form field is invalid, it should gain `aria-invalid="true"`

Good examples include
- Errors appear next to each field that has one on submit
- An error summary appears summarizing which fields have what errors. There can also be a link to the first or all of the error fields, which would just focus the field when clicked.

## Input Purpose

### The purpose for each common input field that collects an individual's personal data MUST be programmatically defined based on the list of 53 Input Purposes for User Interface Components

When the purpose is defined, the screen reader (or password manager or address manager) can help the user autofill, or show the user's custom icons instead of the label for users who prefer images. The values from the list of 53 are used with the HTML5 `autocomplete` attribute

[Click here to see the full list of purposes](https://www.w3.org/TR/WCAG21/#input-purposes). They include:
- Name types like full name, given name, family name, nickname, credit-card name
- username, new-password, and current-password
- address types
- credit card info types

This criterion only applies to text fields asking for information about the user themselves, not others.

#### Good Example
```html
<input class="loginPassword" type="password" id="loginPassword" name="password" aria-required="true" autocomplete="current-password" required="required" oninvalid="this.setCustomValidity('Enter password to login')" oninput="this.setCustomValidity('')"/>
```

#### Success Criterion 1.3.6 Identify Purpose (AAA)

This criterion allows for marking up the purpose of other UI components, like links, to allow for replacement of text on the page with familiar vocabulary or symbols.

There are attributes like `aria-function` to identify a link's purpose and `aria-importance` to identify its importance you can use.