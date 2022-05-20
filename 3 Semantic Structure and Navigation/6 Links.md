# Links

Links don't require special work to make them accessible to screen readers, but there are best practices to follow

## Designate Links Correctly

### Links MUST be semantically designated as such

This can mean:

- `<a>` with a valid href value
- `<div role="link" tabindex="0">` when retrofitting legacy code
    - JavaScript would have to handle the navigation and ensure tab and enter behave correctly

Bad is when you style something to look like a link and attach a click handler. It's not accessible by keyboard.

### Links and buttons SHOULD be designated semantically according to their functions

What is the difference between links and buttons?

- **Links** take users to different locations, either a new page or a new location on the current page
- **Buttons** activate scripted functionality - make a dialog appear, expand a disclosure, or submit form data (which
  can trigger navigation)

#### Screen reader users are informed whether something is a button or a link

Screen readers say "button" or "link" before reading those kinds of elements. It's important to use the correct element
for the correct type of action so people know what to expect, and find what they're looking for in a set of links or
buttons.

DON'T RELY ON ELEMENTS TO AVOID STYLING.

## Link Text

### A link MUST have programmatically determinable text, as determined by the accessible name calculation algorithm

A link must have a text-based name associated with it so that screen readers can read something to users. If a link has
no name associated with it, most screen readers will read the link destination in the href as a way to give users some
sort of clue to the purpose of the link.

The order screen readers look for an accessible name:

1. aria-labelledby
1. aria-label
1. Text contained between the opening <a> and closing </a> elements (including alt text on images)
1. title attribute (note that this is considered a last resort method for screen readers to find something; it should
   not be considered a primary technique for giving names to links)

Some good examples:

#### Good Example: Link text within the `<a>` element

`<a href="https://dequeuniversity.com/contact/">Contact Us</a>`

#### Good Example: Link text from the alt attribute of the img Element

```html
<p>
    <a href="https://dequeuniversity.com/curriculum/">
        <img src="info.png" alt="Web accessibility curriculum">
    </a>
</p>
<p>
    <a href="http://www.deque.com">
        <img width="93" height="33" alt="Deque Systems"
             src="deque_logo.png">
    </a>
</p>
```

#### Good Example: Using aria-label to override native link text

```html
<p>
    The National Museum of African American History and Culture
    was established in 2003 by an Act of Congress, making it the
    19th Smithsonian Institution museum.
    <a href="https://www.si.edu/Museums/african-american-history-and-culture-museum"
       aria-label="Read more about the National Museum of
      African American History and Culture">
        Read more...
    </a>
</p>
```

#### Good Example: Supplemental link text using hidden text

```html

<head>
    <title>Museum Information</title>
    <style>
        .visually-hidden {
            position: absolute;
            clip: rect(0 0 0 0);
            border: 0;
            height: 1px;
            margin: -1px;
            overflow: hidden;
            padding: 0
            width: 1px;
            white-space: nowrap;
        }
    </style>
</head>
<body>
<p>
    The National Museum of American History is devoted to the scientific,
    cultural, social, technological, and political development of the United States.
    <a href="https://www.si.edu/Museums/american-history-museum">
        Read more
        <span class="visually-hidden">
        about the National Museum of American History
      </span>...
    </a>
</p>
</body>
```

#### Good Example: Using aria-label to provide link text for background images

A common technique for making links to social media sites is to use background images assigned to links. This technique
looks fine to sighted users, but it leaves links without an accessible name unless some other technique is applied. In
this example, aria-label supplies text to the link that screen readers can communicate to users.

```html
<a href="https://www.facebook.com/dequesystems/" class="facebook"
   aria-label="Deque's Facebook page"></a>
```

### The purpose of each link SHOULD be able to be determined from the link text alone

Screen reader users often list to links out of context. Good examples:

```html
<p>Learn more about <a href="/products.html">our products</a>.</p>
<p>Read a fascinating article about the
    <a href="http://tinyurl.com/c3z77jt">resident microbes in the human body</a>.</p>
<p>Our <a href="surpassed.html">second quarter earnings</a>
    have surpassed investor expectations.</p>
```

### The link text SHOULD NOT repeat the role ("link")

Screen readers will say "link" and then read the link text, so there is no need to include the word "link" in the link
text.

### Features such as labels, names, and text alternatives for content that have the same functionality across multiple web pages MUST be consistently identified

Links that go to the same place must have the same name across pages. Links that go to different places must have
different names across pages

## Links to External Sites, New Windows, and Files

### A link that opens in a new window or tab SHOULD indicate that it opens in a new window or tab

It can be helpful to users to know when a link will open a new window. Including a text indication (e.g. "opens in a new
window") or an icon with equivalent alt text are two of the most common ways to indicate this. Ensure the indication is
available to both sighted users and blind screen reader users

```html
<p>
    <a href="https://dequeuniversity.com" target="_blank">Deque training
        <img src="newWindow.png" alt="opens new window" width="16" height="16">
    </a>
</p>
```

Using CSS and ARIA to indicate a link opens a new window:

```html
<p>
    <a aria-describedby="a11y-message--new-window" class="icon--new-window"
       href="https://dequeuniversity.com" target="_blank">Deque training</a>
</p>
<span aria-hidden="true" class="visually-hidden" id="a11y-message--new-window">
    (opens new window)</span>
```

In the code above, the class icon--new-window on the anchor tag can be used to inject an icon via CSS (glyph icon) after
the link text. The <span> with id="a11y-message--new-window" provides the text "opens a new window" as a single instance
on the page that is hidden both visually using the CSS clip method and from screen readers using aria-hidden="true".

**`aria-describedby` and `aria-labelledby` WILL access content that is inside a container hidden using aria-hidden="
true".** This allows the screen reader to read "opens new window" when the keyboard focus is placed on the links, but
screen reader users won't find that message when browsing the page.

### A link to a file or destination in an alternative or non-web format SHOULD indicate the file or destination type

Like in a PDF, Word Document, etc., it's helpful to indicate the file type a link will open in the link text itself.

```html

<ul>
    <li>
        <a href="https://dequeuniversity.com/screenreaders/survival-guide">
            Screen Reader Survival Guide
        </a>
    </li>
    <li>
        <a href="https://dequeuniversity.com/assets/pdf/screenreaders/survival-guide.pdf">
            PDF version of the Screen Reader Survival Guide
        </a>
    </li>
</ul>
```

### A link to an external site MAY indicate that it leads to an external site.

It can be helpful to users, but is not required. Should be perceivable by screen reader users and sighted users. Can use
text or an icon with alt text

## Visually Distinguishable from Text

### Links MUST be visually distinguishable from surrounding text

Sighted users must be able to tell the difference visually between link text and the surrounding text so they know what
is clickable.

DO NOT USE COLOR ALONE FOR THIS

Common ways to do this:

- Different color text, plus underline always
- Different color text, plus underline only on hover an focus.
    - This is dangerously close to indicating with color alone. It's discouraged but allowable if the contrast ratio is
      at leas 3:1 between the linked text and non-linked text, and the underline is visible on keyboard focus and hover.
- Different background color on hover and focus
    - Similar to above
- Add an outline or border on hover and focus
- Placement in a navigation menu
    - Sighted users understand that items in a menu are clickable if the menu is styled in a way that makes it obvious
      that it's a menu. This is a pretty subjective technique, because it depends on design trends that change.

## Visual focus indicator

### All focusable elements MUST have a visual focus indicator when in focus

Browsers typically do this by default with a dotted outline or solid outline. The dotted line can be difficult to see,
especially for low-vision users. Leaving the default focus indicator intact is sufficient for minimal compliance, but
can be better.

DON'T DO THIS:

```css
:focus {
    outline: none;
}
```

### Focusable elements SHOULD have enhanced visual focus indicator styles

Enhancing the focus (and hover) states of clickable items is very helpful to low-vision users. Consider all of these:

- links — a:focus {...}
- buttons — button:focus {...}
- inputs — note that a single style may be sufficient for all inputs, depending on the design (e.g. input:focus {...},
  but the styles can also be specified for individual inputs:
    - text inputs — input[type=text]:focus {...}
    - image inputs — input[type=image]:focus {...}
    - submit buttons — input[type=submit]:focus {...}
    - radio buttons — input[type=radio]:focus {...}
    - All other input types
- checkboxes — input[type=checkbox]:focus {...}
- drop-down selection inputs — select:focus {...}
- textarea fields — textarea:focus {...}
- ARIA controls:
    - ARIA links — [role=link]:focus {...}
    - ARIA buttons — [role=button]:focus {...}
    - ARIA inputs — [role=radio], [role=checkbox], etc.
    - ARIA tabs — [role=tab]:focus {...}
    - All other focusable custom ARIA controls
- All other focusable items

## Navigating links with screen readers

More ways to use a screen reader

- Use the tab key
- List all links
  - sorted in page order or alphabetically
- Skip from link to link
- Navigate to unvisited links only
- Navigate to visited links only