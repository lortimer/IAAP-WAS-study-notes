# 4 Description

## Using aria-describedby

NOT part of the accessible name computation. Meant to give supplemental information about an element. Don't use it unless it's needed.

Screen readers first read the name, then the description.

## If the aria-describedby text is critical, it MUST be available to sighted users, and MUST be available in the document context (not just when the focus is on the element with the aria-describedby attribute) as text readable by screen readers

### Good Example: Extra information about a form field is given via aria-describedby

```html
<label for="newPassword">Choose a new password:</label> 
<input type="password" id="newPassword" aria-describedby="pwdInfo"> 
<span id="pwdInfo">Minimum 8 characters, with both letters and numerals</span>
```

## Support for aria-describedby

1. The described element must have a semantic role, screen readers will not read aria-describedby text assigned to `span`s or `div`s.
2. In many cases, the item must be natually focusable, like links or buttons.
3. It's more likely that aria-describedby is supported by items that can have accessible names like images and tables. Paragraphs, headings, list items and lists, are considered text strings describing themselves, so the description may not be read.