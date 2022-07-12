# Typography

The way text is presented can disable people with some cognitive, language, learning, and low-vision disabilities.

Typographical recommendations below align with level AAA WCAG requirements.

## Legibility of fonts

### Fonts SHOULD be easily readable by sighted users

Which fonts are easy to read? The best the class can say is to avoid fancy, specialty fonts and stick to standard ones.

Be careful with sans-serif fonts that captial I and lowercase L are not easily confused in the context of the text on the page.

Also, no joke, one of the bad examples is wingdings. As if a developer would put wingdings on the page assuming most people could read it.

## Spacing of the Lines and Paragraphs

### Line spacing SHOULD be at least 1.5 (150%) within paragraphs

But under most circumstances, line spacing shouldn't exceed 2.0 (200%)

### Paragraph spacing SHOULD be at least 1.5 times the line spacing

This will leave sufficient whitespace to divide the paragraphs. The inter-paragraph space should not exceed 2 times the line spacing.

## Column Width

### The number of characters or glyphs per line in any section or column of text SHOULD NOT exceed 80 (40 characters in Chinese, Japanese, or Korean)

This doesn't mean you have to fix the width of a column. As long as text reflows when the user narrows the window or changes the text size, the user can create the layout they need.

You can use CSS to set column widths that average 80 characters at any given zoom level / font size, but that is a huge pain and I think should be reserved for special circumstances.