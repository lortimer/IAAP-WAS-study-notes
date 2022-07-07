# SVG as img src

## Overview

There are multpile was to embed an SVG into a web page:

1. Utilize the `<img>` tag and reference the SVG file as the source (e.g. `<img src="SVGFile.svg" alt="some alt text">`).
2. Embed the SVG directly (inline) into your existing HTML code, using the `<svg>` element.
3. Embed the SVG in an `<iframe>` or `<embed>` tag, or referenced as the data attribute through an `<object>`.

Obviously, numbers 1 and 2 are great and you shouldn't do number 3. What a hack.

Using `<img>` with an SVG source is good for non-complex images. The HTML file size is smaller, the image can be cached by the browser, and you can use the image in multiple places without repeating the SVG code.

However, with this method, the SVG cannot be manipulated by Javascript or CSS for animation, coloring, or style. If you need that, having the SVG inline is better. Complex images may be more accessible if they are inline because their source code is available to assistive technologies.

You can get the best of both worlds by componentizing your SVG image to make it both inline and reusable.

### All SVG `<img>` elements SHOULD be set to role="img".

This ensures assistive technologies see it as an image (as opposed to what?)

**Take Note!** This is the correct markdown, despite the repetition:

```html
<img src="somesvg.svg" alt="Some SVG" role="img">
```

### All SVG `<img>` elements MUST have meaningful, concise alternative text (via alt, aria-label, or aria-labelledby)

Of course