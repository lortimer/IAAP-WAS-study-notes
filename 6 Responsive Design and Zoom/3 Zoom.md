# Zoom

Some users need to zoom to be able to see elements. Allow zoom without breaking functionality, and don't disable zoom.

## Text Resize/Zoom

Most browsers allow you to zoom only text and no other elements, effectively increasing just the font size of all text on the page. Containers the text is in don't change size. It can be difficult to design in a way that allows text-only zoom.

### The page SHOULD be functional when only the text is magnified to 200% of its initial size

Using static pixel sizes is very bad for this. Using `em` or `rem` to define the size of text containers will mean that text-only zoom will resize those containers as well as the text.

One of the two dimensions can be static pixels or percent of the page as long as the other is based on `em`s, fits to its content, or no height is assigned.

### The spacing between letters, words, lines of text, and paragraphs MUST be adjustable without loss of content or functionality

**For English text** ensure no loss of functionality when the following changes are made with custom CSS:

- Line height (line spacing) to at least 1.5 times the font size
- Spacing following paragraphs to at least 2 times the font size
- Letter spacing (tracking) to at least 0.12 times the font size
- Word spacing to at least 0.16 times the font size

## Content Reflow

### Content MUST NOT require scrolling in two directions (both vertically and horizontally) — even when the viewport is set or zoomed to 320 CSS pixels wide (for vertically-scrolling content) or 256 CSS pixels high (for horizontally-scrolling content) — unless both scrolling directions are essential to the usage or meaning of the content

This essentially means don't allow a page to scroll in the direction the text moves (horizontal for English) when it is zoomed. If that's going to happen, it'll most likely happen before reaching 400%. Never allowing pages to scroll horizontally is probably a good heuristic.

Exceptions to this rule are ok when scrolling in both directions is required for some reason. This includes large tables or graphics or toolbars that just need a whole lot of buttons in them

## Allowing Mobile Zoom

### The page MUST allow users to zoom in on mobile devices

Pinch-to-zoom is very important for people on mobile devices. As of iOS 10, Safari ignores attempts to disable zoom using meta viewport properties.

The two methods of disabling pinch-to-zoom are below, when applied to the content attribute of `<meta name="viewport" content="...">`:
- `user-scalable=no`
- `maximum-scale=1.0`

2.0 is the minimum acceptable value for `maximum-scale`, but up to 5.0 is encouraged. Maximum is 10.0.

## Linear Text Reflow

These are recommendations on wide screens, not success criteria. They are in line with best practices on narrow screens.

### Let the Main Content Fill the Width of the Viewport

Filling the entire width of the viewport (with some padding) is good practice so the content takes up as much space as possible on small screens. 

### Eliminate Multiple Columns

The wider your screen, the more appropriate columns are. It's hard to read very wide paragraphs without losing your place.

Many sites now use a single column (maybe with some settings on the side if the screen is wide enough) to make the design on mobile and desktop similar. This makes it easy to develop, but is not absolutely necessary.

### Linearized Content Helps Screen Reader Users

This makes it harder for reading order and display order to get out of sync.

### Eliminate Most Floating Objects

Meaning images with text around them. Better for them to be in their own div and take a full row.

### Eliminate Horizontal Scrolling/Panning

### Allow Text to Reflow by Eliminating Fixed Widths and Minimum Widths

Fixed and minimum widths are the main causes of horizontal scrolling.

## Magnification Visual Quality

### Text SHOULD magnify losslessly, or with minimal visual degradation, to retain readability

i.e. Don't use images of text.

### Icons and graphics SHOULD magnify losslessly, or with minimal visual degradation

i.e. Use SVG or provide 2x minimum sizes for raster images.