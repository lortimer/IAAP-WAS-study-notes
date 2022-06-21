# Image Maps

An image map is an image with clickable areas, defined by the `<area>` tag.

A good example from the course looks like the following. It's an image of the solar system, and each planet is clickable.
```html
<img src="solar_system.jpg" alt="Solar System" width="472" height="800" usemap="#Map1">
<map name="Map1">
    <area shape="rect" coords="115,158,276,192"
          href="http://en.wikipedia.org/wiki/Mercury_%28planet%29" target="_blank" alt="Mercury">
    <area shape="rect" coords="115,193,276,234"
          href="http://en.wikipedia.org/wiki/Venus" target="_blank" alt="Venus">
    <area shape="rect" coords="118,235,273,280"
          href="http://en.wikipedia.org/wiki/Earth" target="_blank" alt="Earth">
    <area shape="rect" coords="119,280,272,323"
          href="http://en.wikipedia.org/wiki/Mars" target="_blank" alt="Mars">
    <area shape="rect" coords="119,324,322,455"
          href="http://en.wikipedia.org/wiki/Jupiter" target="_blank" alt="Jupiter">
    <area shape="rect" coords="118,457,352,605"
          href="http://en.wikipedia.org/wiki/Saturn" target="_blank" alt="Saturn">
    <area shape="rect" coords="119,606,308,666"
          href="http://en.wikipedia.org/wiki/Uranus" target="_blank" alt="Uranus">
    <area shape="rect" coords="117,664,305,732"
          href="http://en.wikipedia.org/wiki/Neptune" target="_blank" alt="Neptune">
</map>
```

This was a really frickin' sweet feature back in 2000, but I think now is so specialize as to not be useful almost ever.

## The alternative text for the `<img>` of a client-side image map MUST be available as programmatically determinable text

In our example, the image has an alt text, as do each of the planet areas.

As always, the following apply:

### The alternative text for the <img> element of a client-side image map MUST be meaningful (accurately describing the purpose or author's intent in a way that is useful to people who cannot see the image)

### The length of the alternative text for the <img> element of client-side image maps SHOULD be concise (no more than about 150 characters)

## The alternative text for the <area> of a client-side image map MUST be available as programmatically determinable text

Just like they are individual images

As always, the following apply:

### The alternative text for the actionable <area> element of a client-side image map MUST be meaningful (accurately describing the purpose or result of the action in a way that is useful to people who cannot see the image)

### The length of the alternative text for the <area> element of client-side image maps SHOULD be concise (no more than about 150 characters)

## Server-side image maps SHOULD NOT be used when a client-side image map (or other method) can accomplish the same functionality

Server-side image maps work by passing mouse click coordinates to a server-side script, which then determines what was clicked.

Because server-side image maps require the use of a mouse, they are not accessible to people who use keyboards (including people who use screen readers) or speech commands.

The odds this is ever useful information to me are astronomically low. Most web apps are not rendered server-side these days, and images maps are super rare also.