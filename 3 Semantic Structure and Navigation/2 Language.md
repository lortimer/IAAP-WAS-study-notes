# Language

Screen readers can read many different languages. It looks for one specified in the document and falls back to reading the page in the user's default language. It will be unintelligible if it guesses wrong.

Most people only have one, but some people use multiple languages.

## Primary Language of a page

### The primary language of the page MUST be identified accurately on the `<html>` element.

E.G. `<html lang="en">`

### The primary language of the page MUST be identified with a valid value on the `<html>` element.

## Language of Parts within the page

### Inline language changes MUST be identified with a valid lang attribute.
If a passage or word is to be pronounced in another language, it should be specified. A good example is language links.

```html
<p>While in Spain, my friend tried to speak Spanish, 
but she wasn't very good. Everyone kept saying 
&quot;<span lang="es">No comprendo nada de lo que dices.</span>&quot;</p>
```

## Language Codes

### The language code MUST be valid
Support for 2-letter codes is better than for 4-letter ones.