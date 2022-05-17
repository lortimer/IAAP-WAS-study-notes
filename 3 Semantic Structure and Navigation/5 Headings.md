# Headings

Headings help with content organization and navigation. They provide a clear structure of a document, benefiting all users. In many systems, headings can be used to automatically create a table of contents

Headings also improve SEO by highlighting the important parts of a web page. **Don't abuse this to create a bunch of keywords**. Too many headings for SEO makes the page confusing for people.

## Real Headings

### Text that acts as a heading visually or structurally SHOULD be designated as a true heading in the markup.

You can't just make text big, bold, and beautiful, you have to also mark it as a heading.

In a pinch, as when retrofitting a bad old site, you can do the following:
```html
<div role="heading" aria-level="1">
    Screen readers will recognize this as a heading level 1
</div>
```

### Text that does not act as a heading visually or structurally SHOULD NOT be marked as a heading.

**_DON'T JUST USE THE HEADINGS FOR THEIR DEFAULT STYLING, LAZYBONES!_**

## Meaningful Text

### Headings MUST be accurate and informative

Like all accessible text, headings must be descriptive enough for users to understand what they will see in that section.

When a screen reader user reads a heading, it reads the level, heading text, and alt text of images in the heading.

### Heading text SHOULD be concise and relatively brief

## Outline/Hierarchy of Content

### Headings SHOULD convey a clear and accurate structural outline of the sections of content of a web page

As with page layout, create the structure of the content first, then figure out how to style it.

The Heuristic: If you could only read the headings on a page, could you tell what each section was about and where to find the information you need?

### Headings SHOULD NOT skip hierarchical levels.

The lower-level headings relate logically to the headings above them.

Don't skip headings at the top level, start with `h1`.

Don't skip headings within another, like `h1` --> `h3`

## Heading Level 1 Best Practices

### The beginning of the main content SHOULD start with `<h1>`

The main content of the page should begin with an `h1`. Anything before the main content of the page should not be marked with a heading, like a nav. Screen-reader users can skip directly to the first `h1` as a way to skip navigation and other stuff.

### Most web pages SHOULD have only one `<h1>`

Common exceptions:
- A modal or overlay can have its own `h1` because it's on top of the page. There's no confusion because the heading of the modal and the heading of the page are not interactable at the same time.
- Index pages of several blog articles, where each article starts with an `h1`. This doesn't have to be an exception because each article could begin with an `h2`.

## Navigating Headings with Screen Readers

Another section with information about specific screen readers.
- List all the headings
  - Can sort headings alphabetically or as they are in the document.
  - JAWS displays them with their heading level
  - NVDA uses a tree view
- Navigate from one heading to the next
- Navigate to headings of a certain level
  - only supported by some screen readers