# Navigation Within Pages

In general, you make intra-page navigation work well by creating sound semantic structure because screen readers rely on that for navigation.

There are some things that don't have good semantic equivalents in HTML yet. Also, sighted keyboard users don't have access to all the shortcuts that screen readers have, so there are things to make this easier for them.

## Skip Navigation Links

### A keyboard-functional "skip" link SHOULD be provided to allow keyboard users to navigate directly to the main content

This is helpful because the main content rarely comes first. There's usually some sort of header bar with stuff in it.

Good Example:
```html
<div id="skipnav"><a href="#mainContent">Skip navigation</a></div>

<!-- the header, navigation, etc. go here -->

<main id="mainContent" tabindex="-1">
    <!-- the main content goes here -->
</main>
```

#### IMPORTANT NOTE

Some browsers like Safari require the link destination to either:
- Be natively focusable (e.g. link, button, or form element)
- Have a `tabindex` value

If the intra-page link destination is not focusable, the page will scroll to the right place, but the focus will not move there! When the user hits tab, they will be back up at the top of the page!

##### The Solution

Using `tabindex="-1"` solves this problem, and doesn't interfere with natural tab order.

### The "skip link" SHOULD be the first focusable element on the page

### A skip link MUST be either visible at all times or visible on keyboard focus

If you make it hidden, don't use `display:none`, because then the keyboard can't see it. You can use the CSS `clip-path` property, or another method with better browser support.

## Table of Contents

### A table of contents for the page MAY be included at the top of the content or in the header.

Benefits:
- Increase understandablility of the page by summarizing its contents
- Improve navigation by allowing users to go to the part they want
  - Especially sighted keyboard users who don't use a screen-reader

### If a table of contents for the page is included, it SHOULD reflect the heading structure of the page

## Reading Order and Tab/Focus Order

### The DOM order determines the reading order and tab

CSS positioning techniques can make the visual layout not match the DOM order.

Dynamically adding or changing content can put things in unexpected locations. Always be aware of the user's keyboard focus when dynamic changes to content occur. People don't navigate backward to find out if something new has appeared.

### The reading order MUST be logical and intuitive

Turn off style sheets to check reading order without using a screen reader.

### The navigation order of focusable elements MUST be logical and intuitive

It should make sense to people who can see the page, too. As a sighted keyboard user, sometimes the tab order of forms is unintuitive and frustrating

### `tabindex` of positive values SHOULD NOT be used

You can customize tab order this way, but you should not!

1. It causes a dsicrepancy between tab order and reading order
2. It removes the items from their natural tab order, and puts them **first** in the tab order. **`tabindex=1` comes before `tabindex=0`**! And then that item is not in the natural tab order!

## Single-Key Shortcuts

### If a single-character-key shortcut exists, then at least one of the following MUST be true: single-character-key shortcuts can be turned off, remapped, or are only active when the relevant user interface component is in focus

This applies to upper- and lower-case letters, punctuation, number, and symbol characters.

Single-character shortcuts can get in the way for users who interact with their device with speech, because they often use words or strings of letters as shortcuts. Even dictating a word can set these shortcuts off.

Giving users the ability to turn off, remap, or limit the activation of these shortcut solves the problem. This is why Gmail has these shortcuts turned off by default.

These shortcuts also cause issues for people with mobility issues, who may tap a key accidentally.

## Paginated Views

### A paginated view SHOULD include a visible method of informing users which view is the currently active/visible view.

Via styling

### A paginated view SHOULD include a method of informing blind users which view is the currently active/visible view

Generally use `aria-current` for this