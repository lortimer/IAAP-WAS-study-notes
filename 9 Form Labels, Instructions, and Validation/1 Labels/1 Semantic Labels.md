# Semantic Labels

All for inputs and controls need to have a label that is understandable to all users.

## Semantic Labels

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