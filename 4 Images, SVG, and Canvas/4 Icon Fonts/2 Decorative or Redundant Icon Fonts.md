# 2 Decorative or Redundant Icon Fonts

## Decorative or redundant icon fonts SHOULD be set to `aria-hidden="true"`

If an instance of an icon font duplicates the meaning of the adjacent text, screen reader users would not benefit from hearing both the text and the icon font's alternative text, so it is best to set the icon font to `aria-hidden="true"`.

### Good Example

In this example, the link is read as "link Help", so more text is not needed

```html
<p>
   <a href="#">
      Help 
      <span class="fa fa-question-circle" aria-hidden="true"></span>
   </a>
</p>
```

### Bad Example

In this example, screen readers will say, "link Help graphic Help

```html
<p>
   <a href="#">
      Help 
      <span class="fa fa-question-circle" role="img" aria-label="Help"></span>
   </a>
</p>
```