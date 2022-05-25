# Navigation Between Pages

## Navigation Lists

### A navigation list SHOULD be designated with the `<nav>` element or `role="navigation"`

Don't overuse `nav` for every set of links, only the important, main navigation.

When using `role="navigation"`, **put it on a div**. Using it on another element will override that element's semantics!

Good:

```html
<div role="navigation">
    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Products</a></li>
        <li><a href="#">Services</a></li>
    </ul>
</div>
```

Bad:

```html
<ul role="navigation">
    <li><a href="#">Home</a></li>
    <li><a href="#">Products</a></li>
    <li><a href="#">Services</a></li>
</ul>
```

### A navigation list SHOULD include a visible method of informing users which page within the navigation list is the currently active/visible page

Typically this is done by styling the link for the active page

### A navigation list SHOULD include a method of informing blind users which page within the navigation list is the currently active/visible page

Do this with `aria-current="page`!

```html
<ul>
<li><a href="#">Meats</a></li>
<li><a href="#" aria-current="page">Dairy</a></li>
<li><a href="#">Breads, Pasta, & Cereals</a></li>
</ul>
```

## Consistency

### Navigation patterns that are repeated on web pages MUST be presented in the same relative order each time they appear and MUST NOT change order when navigating through the site

This is fairly intuitive, but it's easy to think of how a developer or designer would overlook it.