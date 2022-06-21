# Images of Text

## An image MUST NOT include informative text if an equivalent visual presentation of the text can be rendered using real text.

It's ok if the image is purely decorative or the text is essential to the image.

One reason is that raster images can't easily be scaled where styled text can.

### The Big Exception: Logos

WCAG itself makes this exception

## Images MUST NOT include informative text, unless the text is essential (such as a logo), or the font, size, color, and background are customizable

People with low vision need to be able to customize the appearance of the text to be able to read it better. This isn't possible with text in images.

SVGs can contain text with a `text` tag. This is ok because a screen reader can still read it. I don't know if color-changing software can change the colors, but I wouldn't bet on it. Make sure the contrast ratio is good.