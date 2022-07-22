# Presentation, Math, Definition, Note, Directory, and Abstract Roles

## The Presentation Role

The Presentation role is essentially no role. It's the same role that `<div>` or `<span>` have by default. It does not hide the element, it just makes it neutral.

So anyway, don't use it unless you have a really good reason and know what you're doing. Its intended use is "when an element is used to change the look of the page but does not have all the functional, interactive, or structural relevance implied by the element type, or may be used to provide for an accessible fallback in older browsers that do not support WAI-ARIA." - [from here](https://www.w3.org/TR/wai-aria/#presentation)

### Example Use Cases:

- An element whose content is completely presentational (like a spacer image, decorative graphic, or clearing element);
- An image that is in a container with the img role and where the full text alternative is available and is marked up with aria-labelledby and (if needed) aria-describedby;
- An element used as an additional markup "hook" for CSS; or
- A layout table and/or any of its associated rows, cells, etc.

## The Math Role

Math on the Web and MathML is very complicated, there is much more to learn about it if you need to use it.

### Good Example 1

Note the `aria-label` on the div expressing the equation in words in case the MathML is not supported.

```html
<div role="math" aria-label="a cubed plus b squared plus c">
    <math xmlns="http://www.w3.org/1998/Math/MathML">
        <mrow>
            <msup>
                <mi>a</mi>
                <mn>3</mn>
            </msup>
            <mo>+</mo> 
           <msup>
                <mi>b</mi>
                <mn>2</mn>
            </msup> 
           <mo>+</mo>
            <mi>c</mi>
        </mrow>
    </math>
</div>
```

Markdown does not support MathML, so like a browser that doesn't support it, it shows the above source code as plain text:

<div role="math" aria-label="a cubed plus b squared plus c">
    <math xmlns="http://www.w3.org/1998/Math/MathML">
        <mrow>
            <msup>
                <mi>a</mi>
                <mn>3</mn>
            </msup>
            <mo>+</mo> 
           <msup>
                <mi>b</mi>
                <mn>2</mn>
            </msup> 
           <mo>+</mo>
            <mi>c</mi>
        </mrow>
    </math>
</div>

### Good Example 2

This one shows subscripts

```html
<div role="math" aria-label="x sub 1 plus x sub 2 plus x sub 3">
    <math xmlns="http://www.w3.org/1998/Math/MathML">
        <mrow>
            <msub>
                <mi>x</mi>
                <mn>1</mn>
            </msub>
            <mo>+</mo>
            <msub>
                <mi>x</mi>
                <mn>2</mn>
            </msub>
            <mo>+</mo>
            <msub>
                <mi>x</mi>
                <mn>3</mn>
            </msub>
        </mrow>
    </math>
</div>
```

### Support for MathML

When the course was created, math support on screen readers was limited but improving. I don't know when exactly that was, I think around 2014 or 2015. The best was iOS' VoiceOver, then MacOS' VoiceOver which lacked support for navigating an equation. JAWS and NVDA did not support it at all.

According to some internet searching, JAWS and VoiceOver support MathML now, but only if you use Chrome/Edge, Firefox, IE and Safari respectively. NVDA does not support it, but there are 3rd-party software that can add that support if you use NVDA

## The The Definition Role

Not super common or well-supported by screen readers. It marks a section of text as a definition. HTML already provides the definition list `<dl>` structure for this, which has better support.

You should not apply this role to elements that already have semantic meaning, like `<li>` because it will override their default role. Basically, don't use `role="definition"`

## The Note Role

Similar to HTML's `<aside>` and ARIA's `role="complementary"`. The biggest difference is that the note role does not create a landmark region. It is meant to create a note in the context of the content around it. The others are meant to make sense on their own, out of context.

### Good Example

```html
<p>There are ways to safely view a solar eclipse, including using welder's goggles 
rated at 14 or higher, or looking at the projected image of a pinhole camera.</p>

<p role="note"><strong>Important:</strong> Never look directly at the sun with 
your bare eyes, or through a camera, or through binoculars.</p>
```

## The Directory Role

Used to designate a table of contents or other similar directory structure, whether the items are links or not.

### Good Example

```html
<ul role="directory">
    <li>
        <a href="#chapter-1">
            Chapter 1 - The Prophecy
        </a>
    </li>
    <li>
        <a href="#chapter-2">
        Chapter 2 - Paul
        </a>
    </li>
</ul>
```

## Abstract Roles

Abstract roles cannot be used in code, but they are defined in the ARIA spec. They are categories of roles.

- command
- composite
- input
- landmark
- range
- section
- sectionhead
- select
- structure
- widget