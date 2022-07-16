# Animations and Motion

Motion can cause dizziness in people with vestibular disorders (or just anyone), and may be distracting to people with attention disorders (or just anyone)

## Parallax Effects

Parallax is when multiple elements scroll at different speeds. It is frequently used in video games to make a 2-dimensional game appear 3-dimensional, or give the player a sense of distance from the character to background elements. [See this example on youtube](https://www.youtube.com/watch?v=2z4OTRFuLP8) at your own risk, it shows parallax motion.

Parallax is also used on websites that have stylized scrolling on them. [Here is an example created by Dequeue](https://media.dequeuniversity.com/courses/generic/web-multimedia-animations-and-motion/2.0/en/html/parallax/bad1.html)

### Parallax effects SHOULD be kept to a minimum, in terms of the total number of parallax effects, the amount of parallax within each individual effect, and the size of the area affected

### All content and features within parallax scrolling content MUST be accessible by keyboard

### The contrast of the text against all parts of a moving background MUST be a minimum of 4.5 to 1 for small text or 3 to 1 for large or bold text

For some reason, designers think it's ok to put text on top of dynamic photos when they're using parallax.

### Parallax scrolling can decrease usability

Many pages that use Parallax scrolling don't intuitively indicate that the user can or should scroll like other pages do, because they tend to have images that take up the whole screen.

### Parallax scrolling pages can negatively impact SEO

Because they use CSS to hide some things

## Background Videos and Animations

### Important content MUST NOT be conveyed through background videos and animations, unless users have full control over playback, and full access to any required captions, transcripts, and audio descriptions

This should be obvious by this point in the course. Don't do a time-based thing that the user can't control, seek through, pause, etc.

### A method MUST be provided to pause, stop, or hide any background videos or animations that begin playing automatically and which last 5 seconds or more

### A method SHOULD be provided to pause and restart background videos and animations

### The contrast of the text against background videos and animations MUST be a minimum of 4.5 to 1 for small text or 3 to 1 for large or bold text

### Movement within background videos and animations SHOULD be minimal

It focuses the user's attention, so I guess use it for that purpose with care or just frickin don't do it.

### Background videos and animations SHOULD NOT contain sounds

The nightmare of nightmares. Restaurant websites from the mid 2000s all autoplayed video and sound. It was soooooo awful.

## Animations from Interactions

### A user SHOULD be able to disable motion animation triggered by interaction, unless the animation is essential to the functionality or the information being conveyed

Animations that are essential to the functionality of the information on display are allowed. For example, page scrolling. Another example is transitions between slides in a slide deck, especially when the user chooses the transitions themselves.

Web Browsers provide a well-supported CSS media query called `prefers-reduced-motion` ([documented here](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion)), which gives your application access to the user's system setting. You can use it to provide a reduced-motion version of your animation, for example:

```css
.animation {
  animation: pulse 1s linear infinite both;
}

/* Tone down the animation to avoid vestibular motion triggers like scaling or panning large objects. */
@media (prefers-reduced-motion) {
  .animation {
    animation-name: dissolve;
  }
}
```

You can also put a button on your site that lets the user opt out (or opt in?!) of animation.

Note that this success criterion specifically pertains to animations that are "triggered by interaction," meaning as a result of user actions. SC 2.2.2 Pause, Stop, Hide (level A) governs page information that scrolls, blinks, or moves automatically without user interaction, as well as auto-updating content. 