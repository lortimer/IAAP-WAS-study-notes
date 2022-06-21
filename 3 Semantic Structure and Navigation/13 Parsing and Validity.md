# Parsing and Validity

This is checking that your document is valid and is built into most IDEs

## Complete Start and End Tags

### In content implemented using markup languages, elements MUST have complete start and end tags

W3C has an online tool to check your markup: https://validator.w3.org/

Browsers automatically repair some issues like missing tags, so the DOM from the browser is not the source code. If you want to check validity, use the source code.

## Conflicts and duplicates

### IDs MUST be unique within a web page

This one can mess with screen readers, like when it's trying to associate a label with an input or other widget by ID.

### Names, when provided, of block level elements (e.g. landmarks, tables, iframes, etc.) SHOULD be unique within a web page

This is referring to the "accessible name" of the elements, as React Testing Library calls it. The accessible name of a button is the text in the button, not the literal `name` attribute of the button element. Similarly it's a caption for a table and a label for an input.

## Parent-child relationships

### Markup SHOULD adhere to required parent-child relationships of elements and attributes

#### HTML Relationships

Some elements have required parent/child relationships like `li`s and lists.

#### ARIA Relationships

Browsers can't compensate for mistakes in faulty ARIA syntax, so custom ARIA work should be checked carefully.

## Deprecated Markup

### Deprecated markup SHOULD NOT be used

Notice the "should not" - these are not specifically disallowed by WCAG 2.0

#### Deprecated HTML Elements

Usually identified by an IDE, these attributes are deprecated

| Element       | Description                                                                 |
|---------------|-----------------------------------------------------------------------------|
| `<acronym>`   | 	Defines an acronym                                                         |
| `<applet>`    | 	Defines an applet                                                          |
| `<basefont>`  | 	Defines a base font for the page.                                          |
| `<bgsound>`   | 	Defines background sound                                                   |
| `<big>`       | 	Defines big text                                                           |
| `<blink>`     | 	Defines blinking text                                                      |
| `<center>`    | 	Defines centered text                                                      |
| `<dir>`       | 	Defines a directory list                                                   |
| `<font>`      | 	Defines text font, size, and color                                         |
| `<frame>`     | 	Defines a frame                                                            |
| `<frameset>`  | 	Defines a set of frames                                                    |
| `<hgroup>`    | 	Defines a heading group                                                    |
| `<isindex>`   | 	Defines a single-line input field                                          |
| `<noframes>`  | 	Defines a noframe section                                                  |
| `<listing>`   | 	Defines code text                                                          |
| `<noembed>`   | 	Defines code when embedding is not supported                               |
| `<marquee>`   | 	Defines a moving text region, sliding from the right toward the left       | 
| `<multicol>`  | 	Defines multiple-column layout                                             |
| `<nextid>`    | 	                                                                           |
| `<nobr>`      | 	Defines text that should not break to a new line                           |
| `<noembed>`   | 	Defines fallback content for browsers that don't support `<embed>`         | 
| `<plaintext>` | 	Defines a plain text section                                               |
| `<s>`         | 	Defines strikethrough text                                                 |
| `<spacer>`    | 	Defines empty space                                                        |
| `<strike>`    | 	Defines strikethrough text                                                 |
| `<tt>`        | 	Defines teletype text                                                      |
| `<u>`         | 	Defines underlined text                                                    |
| `<xmp>`       | 	Defines HTML example text that displays without interpreting HTML elements | 

#### Deprecated HTML Attributes

Usually identified by an IDE, these attributes are deprecated

| Attribute      | Deprecated when used in                                                                                                                     |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| `alink`        | 	body                                                                                                                                       |
| `abbr`         | 	td and t                                                                                                                                   |
| `align`        | 	caption, iframe, img, input, object, legend, table, hr, div, h1, h2, h3, h4, h5, h6, p, col, colgroup, tbody, td, tfoot, th, thead and tr. |
| `archive`      | 	object                                                                                                                                     |
| `axis`         | 	td and t                                                                                                                                   |
| `background`   | 	body                                                                                                                                       |
| `bgcolor`      | 	table, tr, td, th and body.                                                                                                                |
| `border`       | 	table and object.                                                                                                                          |
| `cellpadding`  | 	table                                                                                                                                      |
| `cellspacing`  | 	table                                                                                                                                      |
| `charset`      | 	link and a                                                                                                                                 |
| `char`         | 	col, colgroup, tbody, td, tfoot, th, thead and tr.                                                                                         |
| `charoff`      | 	col, colgroup, tbody, td, tfoot, th, thead and tr.                                                                                         |
| `classid`      | 	object                                                                                                                                     |
| `clear`        | 	br                                                                                                                                         |
| `compact`      | 	dl, menu, ol and ul.                                                                                                                       |
| `coords`       | 	a                                                                                                                                          |
| `codebase`     | 	object                                                                                                                                     |
| `codetype`     | 	object                                                                                                                                     |
| `compact`      | 	dl, menu, ol and ul.                                                                                                                       |
| `declare`      | 	object                                                                                                                                     |
| `frame`        | 	table                                                                                                                                      |
| `frameborder`  | 	iframe                                                                                                                                     |
| `hspace`       | 	img and object.                                                                                                                            |
| `link`         | 	body                                                                                                                                       |
| `longdesc`     | 	img and iframe.                                                                                                                            |
| `marginheight` | 	iframe                                                                                                                                     |
| `marginwidth`  | 	iframe                                                                                                                                     |
| `name`         | 	img                                                                                                                                        |
| `nohref`       | 	area                                                                                                                                       |
| `noshade`      | 	hr                                                                                                                                         |
| `nowrap`       | 	td and th                                                                                                                                  |
| `profile`      | 	head                                                                                                                                       |
| `rev`          | 	link, a                                                                                                                                    |
| `rules`        | 	table                                                                                                                                      |
| `scheme`       | 	meta                                                                                                                                       |
| `scope`        | 	td                                                                                                                                         |
| `scrolling`    | 	iframe                                                                                                                                     |
| `shape`        | 	a                                                                                                                                          |
| `size`         | 	hr                                                                                                                                         |
| `standby`      | 	object                                                                                                                                     |
| `target`       | 	link                                                                                                                                       |
| `text`         | 	body                                                                                                                                       |
| `type`         | 	li, ol, ul, param                                                                                                                          |
| `valign`       | 	col, colgroup, tbody, td, tfoot, th, thead and tr                                                                                          |
| `valuetype`    | 	param                                                                                                                                      |
| `version`      | 	html                                                                                                                                       |
| `vlink`        | 	body                                                                                                                                       |
| `vspace`       | 	img and object.                                                                                                                            |
| `width`        | 	hr, table, td, th, col, colgroup and pre.                                                                                                  |