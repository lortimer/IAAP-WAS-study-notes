# Labels

## Semantic Labels

All for inputs and controls need to have a label that is understandable to all users.

### Labels MUST be programmatically associated with their corresponding elements

The hierarchy of techniques to achieve this (earlier on the list overrides the others):

1. `aria-labelledby` set to the ID of an element containing text.
    - Clicking the label text will NOT focus the associated control
2. `aria-label`
    - The label text is invisible to sighted users, only useful for screen readers.
3. **`<label>` This is the best option!!**
    - Clicking the label text also focuses the associated control
4. `title` attribute
    - Invisible and usually intended for non-essential information. It does add a tooltip only available to mouse users
      5.`placeholder`
    - Technically allowed as a way to provide an accessible name, but super discouraged because it disappears when the user enters their own text, the defaul styling fails contrast rules, and it is intended for non-essential information.

#### The Best Method: Explicit Label

```html
<form>
  <label for="fname_a">First Name:</label> 
  <input type="text" name="fname_a" id="fname_a">
</form>
```

#### Other Good Examples

Implicit labels almost always work, but there have historically been some minor edge cases, like with an `<input type="number">` on Firefox with NVDA not working.
```html
<form>
  <label>First Name: <input type="text" name="fname1"></label>
</form>
```

`aria-labelledby`
```html
<p><span id="Nickname">Nickname:</span> <input type="text" aria-labelledby="Nickname"></p>
```

`aria-label`
```html
<p><input type="text" aria-label="search"> <input type="submit" value="Search"></p>
```

`title`
```html
<p><input type="text" title="search"> <input type="submit" value="Search"></p>
```

### Labels MUST be available as programmatically determinable text

Don't use empty labels. A screen reader will guess at a good label if the label is missing, but if you specify an empty label, it will read nothing. Also, if you use images in a label, the alt text is read, so make sure it's there.

## Meaningful Label Text

### Labels MUST be meaningful

This is a "good" example because it asks for specific information and makes it clear what is expected. It's bad
because "first" and "last" names are only meaningful to some people.

```html
<label for="name">Name (First and Last):</label> <input type="text" name="name" id="name">
```

### Labels MUST NOT rely solely on references to sensory characteristics

Don't use only color to convey a label. Color contrast for text and symbols needs to meet the minimum standards. All
information conveyed visually in a label must have an alternative text form.

## Icons as Labels

### Icons MAY be used as visual labels (without visual text) if the meaning of the icon is visually self-evident AND if there is a programmatically associated semantic label available to assistive technologies

The example below is okay because the aria label provides meaning to the magnifying glass icon

```html

<p class="center">
    <input type="text" aria-label="Search">
    <button id="search-button" aria-label="Search">
        <span class="fa fa-search"></span>
    </button>
</p>
```

## Placeholder Text as Labels

### Placeholder text MUST NOT be used as the only method of providing a label for a text input

It should also not be used to convey instructions like how to format the text the user is entering, because the user has
to delete any text in the field to see the instructions or label again.

Screen readers kind of support this usage, but not in a good, consistent way. DON'T DO IT.

## Visibility of Labels

### Labels MUST be visible

### For user interface components with labels that include text or images of text, the name MUST contain the text that is presented visually

The accessible name has to match the text the user sees in a label. If they don't match, a user who uses speech control
will not be able to click the element using the label text.

## Proximity of Labels to Controls

### A label SHOULD be visually adjacent to its corresponding element

### A label SHOULD be adjacent in the DOM to its corresponding element

## Multiple Labels for One Field

### When multiple labels are used for one element, each label MUST be programmatically associated with the corresponding element

This doesn't seem too likely to happen these days. The "classic" example is when there are inputs in a table that should
be labelled by the row and column headers. Take this table for example:

<table class="data">
<caption>Edit Program Information</caption>
  <tbody><tr>
    <th scope="col"><span id="id86_program">Program</span></th>
    <th scope="col"><span id="id86_now">Now</span></th>
    <th scope="col"><span id="id86_past">Past</span></th>
    <th scope="col"><span id="id86_date">Date</span></th>
  </tr>
  <tr>
    <th scope="row"><span id="id86_foodstamps">Food stamps</span></th>
    <td><input name="id86_checkbox" aria-labelledby="id86_now id86_foodstamps" type="checkbox"></td>
    <td><input name="id86_checkbox2" aria-labelledby="id86_past id86_foodstamps" type="checkbox"></td>
    <td><input name="id86_textfield" aria-labelledby="id86_date id86_foodstamps" type="text"></td>
  </tr>
  <tr>
    <th scope="row"><span id="id86_tca">TCA</span></th>
    <td><input name="id86_checkbox3" aria-labelledby="id86_now id86_tca" type="checkbox"></td>
    <td><input name="id86_checkbox4" aria-labelledby="id86_past id86_tca" type="checkbox"></td>
    <td><input name="id86_textfield2" aria-labelledby="id86_date id86_tca" type="text"></td>
  </tr>
  <tr>
    <th scope="row"><span id="id86_medical">Medical</span></th>
    <td><input name="id86_checkbox5" aria-labelledby="id86_now id86_medical" type="checkbox"></td>
    <td><input name="id86_checkbox6" aria-labelledby="id86_past id86_medical" type="checkbox"></td>
    <td><input name="id86_textfield3" aria-labelledby="id86_date id86_medical" type="text"></td>
  </tr>
</tbody></table>

The checkbox corresponding to "Food Stamps" and "Now" could use `aria-labelledby="now foodstamps"` assuming `now`
and `foodstamps` are the IDs of the header cell labels. To do this correctly, **you MUST put the IDs on `span`s within
the header cells**. Putting the IDs on the header cells will not always work right.

## One Label for Multiple Fields

### When one label is used for multiple elements, the label MUST be programmatically associated with each of the corresponding elements

Some form inputs require multiple fields, like when you enter your Social Security Number, phone number, or zip code +4.

There are 3 main techniques for this:

1. Combine the fields and use formatting to separate the sections
2. Use off-screen text with CSS to provide hidden `<label>`s
3. Use `aria-label` combined with a traditional `<label>` on the first field in the set.
4. Use a `<fieldset>` for the visible label, and hidden text for the other labels

#### Good Example: off-screen text with CSS to provide hidden `<label>`s

This method is more backward-compatible than using `aria-label`.

```html
<label for="ssn1b">Social Security Number <span class="offscreen">first three digits</span>:
</label>
<input type="text" size="3" maxlength="3" id="ssn1b"> -
<label for="ssn2b" class="offscreen">Second two digits:</label>
<input type="text" size="2" maxlength="2" id="ssn2b"> -
<label for="ssn3b" class="offscreen">Last four digits:</label>
<input type="text" size="4" maxlength="4" id="ssn3b">
```

#### Good Example: Multiple Fields with Only One Visible Label - Use aria-label

When there is a label and an `aria-label`, JAWS and NVDA will read only the `aria-label`, but VoiceOver will read both.

```html
<label for="ssn1">Social Security Number:</label>
<input type="text" size="3" maxlength="3" id="ssn1"
       aria-label="Social Security Number first three digits"> -
<input type="text" size="2" maxlength="2" aria-label="middle two digits"> -
<input type="text" size="4" maxlength="4" aria-label="last four digits">
</p>
```

#### Good Example: Multiple Fields with Only One Visible Label - Use a `<fieldset>`

This is very robust and backward-compatible. Fieldset and legend elements can be tricky to style. Some screen readers will repeat the legend text for every field in the fieldset.

```html
<fieldset>
    <legend>Social Security Number</legend>
    <label for="ssn10" class="offscreen">First three digits</label>
    <input type="text" size="3" maxlength="3" id="ssn10"> -
    <label for="ssn20" class="offscreen">Second two digits:</label>
    <input type="text" size="2" maxlength="2" id="ssn20"> -
    <label for="ssn30" class="offscreen">Last four digits:</label>
    <input type="text" size="4" maxlength="4" id="ssn30">
</fieldset>
```