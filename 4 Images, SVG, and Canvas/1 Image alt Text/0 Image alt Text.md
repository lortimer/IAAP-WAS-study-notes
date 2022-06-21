# Image `alt` Text

This section is about making various types of images accessible. Good alternative text is:

- Programmatically Determinable (screen readers can access the alternative text)
- Meaningful (the alternative text accurately describes the image's purpose or author's intent in using the image).
- Concise (the alternative text does not exceed about 150 characters, and preferably is much shorter than that)

One technique to hide decorative images is with `alt=""`. This only works in HTML, not MS Office docs, where all images must have an alt text.

The overall goal is to give people who are blind an equivalent experience to those who are sighted, or at least get as close as possible without overwhelming them with long text descriptions.

`alt` is the preferred way to add alternative text to images, but there other options evaluated in the following order:


1. aria-labelledby — If there is an aria-labelledby attribute, the text it refers to will override all other values.
1. aria-label — The aria-label text will override all other values (if aria-labelledby is not specified).
1. alt — This is the standard method of providing alternative text (note that the alt text won't be read at all if either an aria-labelledby attribute or an aria-label attribute is present).
1. title — Screen readers will read the title attribute text if no other method is present. Some screen readers (e.g. VoiceOver on macOS) treat the title attribute as an additional description for the image and will read both the accessible name AND the title. Others (e.g. NVDA, JAWS) will not read the title if an accessible name is available through other methods. All screen readers read the title text if no other alternative text is provided.