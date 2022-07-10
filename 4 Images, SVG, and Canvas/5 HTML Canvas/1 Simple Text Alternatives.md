# Simple Text Alternatives

## When `<canvas>` elements are used to display graphics, they MUST be assigned role="img"

It's not automatically treated as an image.

## All `<canvas>` elements MUST have a text alternative

**THE CONTENTS OF A CANVAS ARE NOT RENDERED IN THE DOM OR ACCESSIBILITY TREE**. Either fallback content or ARIA must be used to create text alternative

### Good Example: Aria Label

```html
<canvas id="goodCanvas1" width="700" height="100" role="img"
    aria-label="A red and white circular target with an arrow  
    pointing to the center of the target"  style="margin:auto">
</canvas>
```

### Good Example: Aria Labelled By

You can put text directly in the canvas, but screen readers will treat is as normal text, not text associate with an image. Therefore, use `aria-labelledby` to mark the text as a label for the image.

```html
<canvas id="goodCanvas2" width="700" height="100" role="img"
    aria-labelledby="goodCanvas2Fallback" style="margin:auto">
    <p id="goodCanvas2Fallback">A red and white circular target with an arrow  
    pointing to the center of the target</p>
</canvas><script> 
   /* enter script here to add visual elements to canvas element */ 
</script>
```

## The alternative text for `<canvas>` elements MUST be meaningful