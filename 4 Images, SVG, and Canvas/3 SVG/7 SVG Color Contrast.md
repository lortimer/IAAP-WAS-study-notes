# SVG Color Contrast

## SVG images SHOULD include a base background color behind the important parts of the image, at a minimum

If an SVG image does not have a background color set, the background color of the image itself will change when the user switches into Windows High Contrast Mode. That may or may not be a problem for a given image, but if large portions of the SVG image are transparent, and if they depend on a particular background color on the web page to look correct, the SVG image will probably be difficult to discern when the background color changes.

It is not necessary to completely fill the background rectangle of an SVG image. Parts of the SVG image can remain transparent as long as there are no transparent parts within the SVG that would cause the image to become difficult to understand if those colors were to change. For example, if the assumption is that the background color of the page is white, and if parts of the SVG image are white only because the color of the web page is showing through, those parts of the image will turn black if the user switches to Windows High Contrast Mode with a black background.

The background fill can be any shape, as long as it fills in the important parts of the image.

### Examples

If you have an SVG with black text in it, that text should have a light background color. That way, if high-contrast or dark mode is used, the text is still legible against the newly-dark background.

Without the light background, the black text will blend into the dark background.

## SVG images SHOULD be styled to ensure compatibility with Windows High Contrast Mode

In general, SVGs retain their color in high-contrast mode (or do they? Find out for yourself!)

If CSS is used to style the SVG, this is **not true** - high-contrast mode overrides CSS colors.

IE and Edge provide media queries to detect high-contrast mode. Other browsers do not, but you can use javascript to detect it. The solution they linked to was to create a div with a specific color, then check its computed color. If the computed color is different from the original, something like high-contrast mode has changed the color.