# Complex Alternative Text

## Complex `<svg>` images MUST have meaningful, concise alternative text AND MUST have a more complete long description

Same rules apply as long descriptions for other image types

## A `<desc>` element MUST be used to provide a detailed description of a complex `<svg>` if it is not provided in any other way

This is a fallback rule. It is best to provide the description another way, such as text in the document. The `<desc>` is only available to screen reader users. 

## The `<desc>` attribute of an `<svg>` element MUST be programmatically associated with the `<svg>` element (via aria-labelledby)

Again, `<desc>` is not well supported, so using `aria-labelledby` is mandatory anyway.

## The length of all associated alternative text (including `<title>` and `<desc>`) for the `<svg>` element SHOULD be concise (no more than about 150 characters)

Have we repeated ourselves enough yet? Provide a long description in the text of the document or link to one.