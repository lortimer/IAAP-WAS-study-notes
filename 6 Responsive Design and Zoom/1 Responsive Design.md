# Responsive Design

Responsive design was invented to accommodate the small screens of smart phones, but had the benefit of serving people with low vision as well. As web content is magnified using the browser's zoom, it eventually reaches resolutions equivalent to mobile devices, so the CSS media queries put in for mobile devices also work in a desktop browser.

The goals of responsive design include ensuring text is big enough to read on devices with small or few pixels and to eliminate horizontal scrolling.

## Responsive Design is Low Vision Design

Mobile devices with their tiny screens forced the invention of responsive design because they effectively disabled almost all of their users.

Large displays disable a smaller set of people who then need to magnify the contents of the screen. Screen magnifiers can magnify anything on the screen, not just the contents of a web browser. Most operating systems come with a built-in solution.

## Responsive Desktop Designs

### Don't Disable Responsive Designs on Desktop Devices

Many users with low vision can't use mobile screens at all and rely on desktop computers and large monitors.

People on the internet say you can do this with Javascript detection of mobile vs. desktop. The process to do it seems pretty difficult in itself.

## CSS Media Queries

### Example Code 

In CSS

```css
@media (max-width: 700px) {
     /* small device styles go here */
}
@media (max-width: 1060px) {
     /* medium size device styles go here */
}
@media (min-width: 1061px) {
     /* large device styles go here */
}
```

Or HTML

```html
<link rel="stylesheet" media="(max-width: 700px)" href="small.css" />
<link rel="stylesheet" media="(max-width: 1060px)" href="medium.css" />
<link rel="stylesheet" media="(min-width: 1061px)" href="large.css" />
```

### Media Types

You can target only specific media types with queries. See below for examples of how to do this. The following media types are defined as part of Media Queries 4 as useable in HTML5:

Media types were originally meant to be used for the media attribute on `<link>` elements. Useful when loading stylesheets, you could specify a media type to selectively load the right stylesheet for the device your page was displayed on, for example:

```html
<link href="print.css" rel="stylesheet" media="print">
<link href="mobile.css" rel="stylesheet" media="screen and (max-width: 600px)">
```

Unfortunately, media types are insufficient for discriminating between devices for a few reasons. Some categories started as distinct but are now too similar to be useful, like `screen` and `handheld` because of smartphones. Some expose truly unique features, like `tty` and `tv`, but since media types are mutually exclusive, most developers wouldn't use highly specific ones. Instead, you can target the unique features of those devices on any device using media features like `grid` or `scan`

- `all`
  - for all media types and devices
- `print`
  - for printers
- `screen`
  - for computer screens, including tablets, phones, etc.

[The following media types are deprecated!](https://drafts.csswg.org/mediaqueries/#media-types) They have been found not to be useful and should not be used!

- `speech`
  - for screen readers
- `embossed`
  - for braille printers
- `tty`
  - Intended for media using a fixed-pitch character grid, such as teletypes, terminals, or portable devices with limited display capabilities. Authors should not use pixel units with the "tty" media type.
- `tv`
  - Intended for television-type devices (low resolution, color, limited scrollability).
- `projection`
  - Intended for projected presentations, for example projectors or print to transparencies. Please consult the section on paged media for information about formatting issues that are specific to paged media.
- `handheld`
  - Intended for handheld devices (small screen, monochrome, limited bandwidth).
- `braille`
  - Intended for braille tactile feedback devices.
- `embossed`
  - Intended for paged braille printers.
- `aural`
  - Intended for speech synthesizers. See the section on aural style sheets for details.
- `speech`
  - Intended for use with screen readers. There is a small subset of CSS that can change how the page content is spoken. For example, by reading punctionation out loud or not.

There are others that are not used much anymore

### Media Features

- `color, min-color, max-color`
  - The number of bits per color component. A grayscale device would be 0.
- `color-index, min-color-index, max-color-index`
  - The number of colors in the color lookup table for the device, e.g. 128, 256, etc.
- `aspect-ratio, min-aspect-ratio, max-aspect-ratio`
  - The ratio of the viewport, with horizontal listed first, then vertical, e.g. 1/1, 2/1, etc.
- `device-aspect-ratio`
  - The ratio of the screen, with horizontal listed first, then vertical, e.g. 16/9.
- `device-height`
  - The height of the screen (not just the height of the rendering area)
- `device-width`
  - The width of the screen (not just the width of the rendering area)
- `grid`
  - Whether the device is grid-based, such as a TTY; allowed values: 1 or 0
- `height, min-height, max-height`
  - The height of the rendering area (the screen may be larger)
- `monochrome, min-monochrome, max-monochrome`
  - The number of bits per pixel
- `orientation`
  - allowed values: landscape or portrait
- `resolution, min-resolution, max-resolution`
  - The pixel density of the device, specified in dpi or ppx
- `scan`
  - Allowed values: progressive or interlace
- `width, min-width, max-width`
  - The width of the rendering area (the screen may be larger)

### Complex Media Query Examples

```css
@media print and (min-resolution: 300dpi) { ... }
@media all and (max-width: 500), all and (color) { ... }
@media screen and (device-aspect-ratio: 16/9) { ... }
```