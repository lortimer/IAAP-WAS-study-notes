# 0 Introduction

`<canvas>` is an element that renders pixels onto the screen. Usually, Javascript is used to draw on the canvas at runtime, and it's often used for charts or games.

`<canvas>` is well supported for rendering, but its content is almost never accessible. Accessibility can be added to the `<canvas>` element itself with ARIA or Javascript. You can allso add "fallback" content within the opening or closing `<canvas>` tags.

SVG is usually better than canvas. Some other rules that will likely be mentioned in this lesson:
- `<canvas>` should not be used to display text.
- `<canvas>` must have an accessible name and description that matches content and visible text
- When used as a mouse/keyboard operable UI control, `<canvas>` must have an accessiblity role