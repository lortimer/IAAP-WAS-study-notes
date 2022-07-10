# Low Vision Accessibility

## All `<canvas>` elements SHOULD have a background fill

Users can change their background color, so if your canvas doesn't have a fill, your image could become very difficult to perceive. A common change for people with low vision is from black text on a white background to yellow text on a black background. If your image relies on the white background, a black background is likely to ruin it entirely.

## If text is required in a graphic, it MAY be more appropriate to use SVG instead of `<canvas>`

This is because text in a canvas doesn't necessarily scale as well. Also, text in an SVG has a better chance of being readable because it can be part of the document.

