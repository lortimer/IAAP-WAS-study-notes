# Complex Text Alternatives

Complex canvas elements like charts and graphs require a full text alternative. Like with other images, this means a long description that is not the alt text, because the alt text should be less that 150 characters.

## All `<canvas>` elements used as complex images MUST have a detailed text alternative

A couple good ways to achieve this:
- Use `aria-label` and if needed, `aria-describedby` to provide a longer description
  - All options for long descriptions are options with `canvas`
- If your complex image is a graph, you should consider displaying the data as a data table in addition to the canvas, since tables are much easier to build accessibly.