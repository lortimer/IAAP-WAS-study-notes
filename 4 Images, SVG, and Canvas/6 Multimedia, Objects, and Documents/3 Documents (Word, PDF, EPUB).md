# 3 Documents (Word, PDF, EPUB)

## An HTML version of non-HTML content SHOULD be made available to users

HTML is the most appropriate format for web content because:
- The accessibility features in HTML are quite mature, in most cases exceeding the accessibility features of non-HTML platforms.
- Users don't need to download the file.
- Users don't need to leave the web browser interface.
- Users don't need to own, download, or install extra software.

Non-HTML documents can be accessible and appropriate in certain situations. PDFs are great for printing, and files like .docx or .xlsx are appropriate for sharing content. At minimum, a summary of the content should be provided in HTML, if not an equivalent HTML version.

## Non-HTML documents MUST adhere to basic accessibility principles

- Give the document a meaningful title
- Provide good heading structure
- Provide alternative text for images
- Designate table headers and ensure the data cells are associated with the headers
- Don't rely on color alone to convey information
- Ensure sufficient contrast between the text and the background
- Choose highly readable fonts

## PDF files MUST be in tagged PDF format

PDF files contain tags much like HTML documents, but they are not required to make a PDF that looks right. An untagged PDF can be "auto-tagged" by software that reads it, but this doesn't usually result in the best experience for users.

The best way to make an accessible PDF is to create an accessible document in an authoring tool like Word, generate a PDF, then use software like Acrobat to check that the tagged document is accessible as intended.

W3C has a [set of guidelines](https://www.w3.org/WAI/WCAG21/Techniques/#pdf) for making PDFs accessible in a WCAG 2.1 way. Surprise Surprise, it's basically the same as WCAG 2.1.

## EPUB files MUST adhere to HTML accessibility principles, and the accessibility principles of any other technologies used within the EPUB document

EPUB is arguably the most accessible format for ebooks. They are flexible in how the document is presented, and their structure is based on HTML.

In contrast, PDF files are meant to retain layout and styling, and are not ideal for ebook reading. The amount of content on a given page cannot change.

## EPUB files SHOULD be in EPUB 3 (most recent) format

It is much better for accessibility than older versions

## EPUB documents MUST adhere to the additional accessibility principles in the EPUB Accessibility specification

- [EPUB Accessibility 1.0 Spec (proposed)](https://idpf.org/epub/a11y/)
- [EPUB accessibility Guidlines](https://idpf.github.io/a11y-guidelines/)