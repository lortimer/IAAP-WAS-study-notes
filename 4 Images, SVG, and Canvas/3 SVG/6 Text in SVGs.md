# Text in SVGs

## Text within `<svg>` elements SHOULD be eliminated OR SHOULD be kept to a minimum

Text in an SVG is scalable and thus good for people with low vision. However, screen reader users will probably hear all of it at once with no way to navigate it, which is especially bad if there are multiple text elements to identify different parts of the image.

The example of text in a chart from previous pages was good, it only had the month and the value for that month. The separate long description provided the meaningful description.

## All informative `<text>` elements inside `<svg>` elements MUST be referenced in the alternative text of the `<svg>` element, or in a long description

Get this:
1. If you don't put `<title>` or `role="img"` in an SVG, screen readers treat it like text and read the text inside, but inconsistently across readers.
2. `<title>` is required for SVGs, but most screen readers won't read it unless you also use `role="img"`
3. If you have both, screen readers will begin to ignore any text elements inside the SVG!

Thus, you need to make any informational text from the image available with `aria-labelledby`

Don't reference text from the image in the `aria-labelledby` if it wouldn't make sense - this is not "informative text"