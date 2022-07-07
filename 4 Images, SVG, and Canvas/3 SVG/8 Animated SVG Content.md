# Animated SVG Content

## SVG animations SHOULD use JavaScript, rather than the `<animate>` element

One way to animate SVGs is with Javascript or CSS. This is the preferred way. The SVG 2 spec is not yet adopted despite
existing for 6 years, but it is moving away from duplicating the features of HTML5 and CSS, opting to rely on them
instead to simplify its own spec.

You can animate SVGs with Synchronized Multimedia Integration Language (SMIL). Internet Explorer does not support SMIL,
but as of June 2022, Microsoft doesn't support IE. IE would simply render the final state of the image.

### Bad Example

Use Javascript or CSS instead! But don't forget about supporting older browsers!

```svg
<svg>
    <title>A blue square with an animation effect that reveals the square, top down.</title>
    <rect width="200" height="200" fill="blue">
        <animate attributeName="height" from="0" to="200" dur="5s" />
    </rect>
</svg>
```

## SVG animations MUST not flash or blink at a rate of 3 times per second or more

## SVG animations MUST NOT auto-play for more than 5 seconds

It's best to let users trigger animation in general

## SVG animations MUST allow users to pause the animation

## SVG animations SHOULD NOT distract the user from the main purpose of the web content