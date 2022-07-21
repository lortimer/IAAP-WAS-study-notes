1 ARIA Overview and Name

## Overview

### What can ARIA do?

It allows you to communicate the following to screen readers:

- labels or names for items
- roles - navigation, main, link, button
- states of dynamic components - selected, expanded, hidden
- other properties of items, like "this item has a popup"
- relationships between items
- live announcements

### ARIA is Useful Only to Assistive Technologies

It does not change anything for sighted users (except when those sighted users are using a keyboard, perhaps ARIA influences the focusable elements of the UI)

### ARIA is Not a Programming Language

You need to use Javascript in combination with ARIA to give your widget functionality. ARIA is only used to signpost the parts of your widget and what they do.

## Name

### The "accessible name" calculation algorithm

The accessible name of an element is calculated by an algorithm. The basics of this algorithm are as follows:

#### 1. `aria-labelledby`

If there is an `aria-labelledby` attribute, the text it refers to will override all other name and label methods.

#### 2. `aria-label`

If there is no aria-labelledby, the aria-label text string will override everything else. Note that the aria-label text is invisible, and only available to assistive technology users.

#### 3. The native HTML text of the element (or native label or alternative text)

This is the preferred method! Only use aria if native HTML won't work in context!

If there is no aria-labelledby or aria-label, the native text of an element will be used (e.g. the text between the opening and closing `<button>` elements, the `<label>` text on a form field, the alt text of an image, etc.

#### 4. `title`

If no other naming methods are available, the `title` will count as the label. Note that the title is best considered as extra, non-essential information, because the `title` is not visible at all times and some users cannot access it at all, for example in browsers that show the title text only on mouse hover.

### `aria-labelledby`

This text is usually visible on the screen. The point of using it is to associate an element with visible text that sighted users understand is labeling something else. You _may_ label something with hidden text, but you're probably putting sighted users at a disadvantage, and at that point you might as well use `aria-label` instead.

The value for `aria-labelledby` is one or more IDs of other lements.

Using `aria-labelledby` with **replace and element's original text**, so don't use it for supplemental information. Some screen readers read both, but not all. Use `aria-describedby` for supplemental information.

In the example below, the button's name is "Roger Roger", not "Submit".

```html
<span id="roger">Roger Roger</span>
<button aria-labelledby="roger">Submit</button>
```

### `aria-label`

`aria-label` contains the accessible name itself, not an ID. It is invisible to the user, only read by assistive tech. There isn't even a tooltip.

It also completely replaces the element's original text, it cannot provide supplemental information. Again, some screen readers read both, but not all.

#### Good Example Usage

Labeling one of many navigation regions:
```html
<nav aria-label="Product Categories">
```

Labeling an unlabeled form input, like a search text box with a "Search" button
```html
<form action="#" role="search">
  <input aria-label="Site Search" name="search" type="search">
  <input type="submit" value="Search">
</form>
```

### Support for aria-labelledby and aria-label

You can use it on anything, but screen reader support is best on: 
- focusable elements 
- semantic elements like `nav`, `footer`, and `header`
- elements in "application regions".

The screen reader, its version, and the mode its in can all vary what support it provides for these attributes. The browser also influences it.