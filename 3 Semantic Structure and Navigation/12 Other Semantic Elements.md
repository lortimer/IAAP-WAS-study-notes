# Other Semantic Elements

Not all screen readers support the other semantic elements.

##`<strong>` and `<em>`

### Critical emphasis in the text SHOULD be conveyed through visual styling
Rather than using `<i>` or `<b>`, you can use `<em>` or `<strong>` respectively.

### Critical emphasis in the text SHOULD be conveyed in a text-based format
However, **all major screen readers ignore these tags**, at least by default.

#### What is critical emphasis?
If the emphasis of a piece of text is not critical to understanding its meadning, it's not necessary to make the emphasis accessible. You have to consider whether the emphasis changes the meaning.

#### How to make "emphasis" accessible
- Use words like "important" or "warning"
  - Visible
  - Hidden visually
- Add an image with appropriate alt text

#### My thoughts on this section
The examples the class listed are not of emphasis, but of warning the user. I suppose someone might use bold to convey a warning, but I wouldn't call that emphasis.

In my opinion, emphasis is a way of marking text so the reader understands a (usually spoken) nuance to the meaning. For example, 

> I didn't lick the _dog_

implies the speaker licked something other than the dog, where

> _I_ didn't lick the dog

implies the dog got licked, but not by the speaker. I would make this emphasis accessible.

On the other hand, some emphasis does not change the meaning, only the intonation of the speaker. J.D. Salinger does this a lot. The story _Teddy_ opens with

> "I'll exquisite day _you_, buddy, if you don'w det down off that bag this minute. And I mean it," Mr. McArdle said.

The italics on the word "you" are meant to give the reader an idea of how the character said the sentence, but don't change the meaning of what he said - it's a threat either way, and there is no chance that any other character would think he was threatening them. In this case, I think it's unnecessary to make the emphasis accessible.

## `<blockquote>` and `<q>`

### The `<blockquote>` element SHOULD be used to designate long (block level) quotations

This element is recognized by most screen readers.

### The `<blockquote>` element SHOULD NOT be used for visual styling alone
### The `<q>` element (for inline quotations) SHOULD NOT be used as the only way to designate quotations

This element is used to add a citation to a quote, and most screen readers ignore it. Quotation marks should be used instead.

## `<code>` and `<pre>`

### Code SHOULD be marked with the `<code>` element and styled to look different from non-code text

This is a visual thing, mostly. Screen readers don't recognize the `<code>` element, so screen-reader users don't benefit from its presence. Other text should be used to denote that something is code, not prose.

### Blocks of code SHOULD be formatted with the `<pre>` element

Also not semantically meaningful to a screen reader. This element stands for "pre-formatted" text. If the block also contains code, you should put a code block inside the pre:

```html
<pre><code>...</code></pre>
```

## Strikethrough/Delete and Insert

### Strikethrough text SHOULD be marked with the `<del>` element

Default is that text is struck-through.

Not supported by screen readers. They read the text but don't indicate that it is struck through

### Critical strikethrough text MUST be supplemented with a text-based method to convey the meaning of the strikethrough

### Text designated for insertion SHOULD be marked with the `<ins>` element

Default is text with underline. Usually this is just for legal documents or a document following that kind of rule set.

Not supported by screen readers. They read the text but don't indicate that it is struck through

### Critical text designated for insertion MUST be supplemented with a text-based method to convey the meaning of the insertion

## Highlighting (`<mark>`)

### Highlighted text SHOULD be marked with the `<mark>` element

Default is text with yellow background.

Not supported by screen readers. They read the text but don't indicate that it is struck through

### Critical highlighted text SHOULD be supplemented with a text-based method to convey the meaning of the highlighting