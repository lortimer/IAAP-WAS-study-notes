# Decorative or Redundant Images

## Images that do not convey content, are decorative, or are redundant to content that is already conveyed in text MUST be given null alternative text (`alt=""`), ARIA `role="presentation"`, or implemented as CSS backgrounds

Providing null alt text with `alt=""` is different from leaving off the `alt` attribute altogether. Screen readers will look for a different source, like the image `src` URL if they find no `alt`.

Examples of decorative or redundant images:
- A house icon next to a link that says "home page"
  - This icon would be redundant if it had alt text that said "home page"