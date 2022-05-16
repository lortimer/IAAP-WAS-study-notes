# Landmarks

Important for navigating within a page. HTML5 gave us the landmarks that were missing before, like `nav` and `main`.

Because landmarks are invisible, we still need to add Skip Nav links for people who navigate with the keyboard, but don't use a screen reader.

## Creating Landmarks

### Landmarks SHOULD be used to designate pre-defined parts of the layout (`<header>`, `<nav>`, `<main>`, `<footer>`, etc.).

Landmarks designate sections of the page layout, while headings designate sections of the page content.

#### HTML5 landmarks and their ARIA equivalents

It is better to use native HTML tags, but using ARIA roles instead is indistinguishable for the end user. It's better practice for code stewardship.

Full support landmarks with their roles:
- `header`, role: "banner"
- `nav`, role: "navigation"
- `main`, role: "main"
- `footer`, role: "contentinfo"
- `aside`, role: "complementary"

There is no HTML semantic element that corresponds to the "search" role. It should be added to the container element that encompasses all elements of a search feature, which should include an `<input type="search">`.

Landmarks with mixed support:
- `section`, role: "region"
  - Most screen readers only list it if it has a name via `aria-label` or `aria-labelledby`.
  - If each section of the content has a heading, screen-reader users can navigate by those, so it's not usually necessary to use the `section` landmark.
  - The ARIA role is not a landmark, even though the element is
- `article`, role: "article"
  - JAWS lists this landmark, others don't.
  - The ARIA role is not a landmark, even though the element is
- `form`, role: "form"
  - Screen readers list forms only if marked with `role="form"`. The element itself is ignored by landmark lists.

## Best Practices for Landmarks

### All text SHOULD be contained within a landmark region

### Multiple instances of the same type of landmark SHOULD be distinguishable by different programmatically determinable labels (`aria-label` or `aria-labelledby`)

E.G. multiple navs should have different labels

### A page SHOULD NOT contain more than one instance of each of the following landmarks: `banner`, `main`, and `contentinfo`.

The ARIA specification states that each of these is to be used once per page. They correspond to a `header`, `main`, and `footer`. HTML5 does not put this restriction on, but it should be followed.

### The total number of landmarks SHOULD be minimized to the extent appropriate for the content

There's no limit on the number of landmarks you can have, but they are for quick navigation, so you should limit their number.

For example, a list of links doesn't always have to be marked as a nav. If it's part of the content or a list of references, it probably doesn't have to be a nav. The nav should be for navigating your site.

## Backward Compatibility

### Landmarks SHOULD be made backward compatible

When supporting older browsers that don't use HTML5 (Before about 2013 for most), you should make them backward compatible.

Some things you can do:
- Make them `display: block` in CSS. Otherwise, they may be displayed inline.
  - Other elements that should be `display: block`:
    - `audio` 
    - `canvas` 
    - `datalist` 
    - `details` 
    - `figcaption`
    - `figure` 
    - `output` 
    - `progress` 
    - `summary` 
    - `video`
- Use Javascript to fix rendering issues in IE8 and below i.e. Polyfills

```html
<!--[if lt IE 9]>
<script>
  var e = ("abbr,article,aside,audio,bdi,canvas,datalist,details,dialog," +
      "figcaption,figure,footer,header,keygen,mark,menu,meter,main,nav,output," +  
      "progress,rp,ruby,rt,section,source,summary,time,track,video,wbr").split(',');  
      for (var i = 0; i < e.length; i++) {
          document.createElement(e[i]);
      }
</script>
<![endif]-->
```

## Navigating Landmarks with Screen Readers

You can use the following methods to navigate landmarks in a screen reader.:
- List all landmarks
- Navigate from one landmark to the next
- Navigate to the main landmark

The reading material lists shortcut keys for these per screen reader. I won't reproduce them here because you learn shortcuts when you use a tool, not by reading about them.