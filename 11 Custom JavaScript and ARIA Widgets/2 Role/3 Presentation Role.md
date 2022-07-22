# Presentation

## The Presentation Role

The Presentation role is essentially no role. It's the same role that `<div>` or `<span>` have by default. It does not hide the element, it just makes it neutral.

So anyway, don't use it unless you have a really good reason and know what you're doing. Its intended use is "when an element is used to change the look of the page but does not have all the functional, interactive, or structural relevance implied by the element type, or may be used to provide for an accessible fallback in older browsers that do not support WAI-ARIA." - [from here](https://www.w3.org/TR/wai-aria/#presentation)

### Example Use Cases:

- An element whose content is completely presentational (like a spacer image, decorative graphic, or clearing element);
- An image that is in a container with the img role and where the full text alternative is available and is marked up with aria-labelledby and (if needed) aria-describedby;
- An element used as an additional markup "hook" for CSS; or
- A layout table and/or any of its associated rows, cells, etc.

## The Math Role