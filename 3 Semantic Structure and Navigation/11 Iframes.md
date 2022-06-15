# Iframes

Iframes are essentially windows from one page into another. They can contain anything a page can, including hidden
Javascript.

Iframes need titles, and their contents are available to screen readers as if they were part of the main document.

## Frame titles

### Iframes that convey content to users MUST have a non-empty title attribute

### The iframe title MUST be accurate and descriptive

#### Good Example:

```html

<iframe
        title="Video: Specify the Language"
        width="560" height="315"
        src="https://www.youtube.com/embed/qyjDrUV_el8"
        allowfullscreen>
</iframe>
```

Without a title, a screen reader might read the URL of the page, just "javascript", or some other piece of text that
doesn't help the user understand what's in the frame.

### Frames MUST have a unique title (in the context of the page)

## Page Title Within an Iframe

### The source page of an iframe MUST have a valid, meaningful `<title>`

This is a WCAG requirement of all pages anyway. The JAWS screen reader actually reads the title of the page in the
iframe instead of the title of the iframe itself.

Best practice would be to make the iframe title match the title of the page in the iframe.

## Semantic structure across iframes

### Screen readers allow cross-frame navigation of semantic elements

This is not a requirement, but a reality. The user has full access to the content in an iframe with a screen reader and
keyboard, and in many ways, the iframe is part of the same document. For example, if there are 5 headings in the main
page, and 3 in the iframe, a screen reader will list all 8 headings.

### The heading hierarchy of an iframe SHOULD be designed to fit within the heading hierarchy of the parent document, if possible.

If possible create a hierarchy where the headings in the iframe fit into the heading structure of the page.

Since iframes are used to show 3rd-party content most of the time, this isn't always possible and isn't required.

## Hiding iframes that don’t contain meaningful content

### Hidden frames or frames that do not convey content to users SHOULD be hidden from assistive technologies using aria-hidden="true"

If the frame is only for javascript, or contains only decorative elements, it should be hidden.