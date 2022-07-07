# Inline SVGs

A major advantage to embedding the `<svg>` element directly in the HTML is that you can use JavaScript and CSS to
manipulate the image.

There are some downsides:

- Assistive technology support for SVGs is not consistent. The information below provides the best experience across a
  wide range of ATs.
- Increased file size
- Image cannot be cached
- Multiple "sources of truth" if you want to reuse the image

## All `<svg>` elements MUST be set to role="img".

## All informative or actionable `<svg>` elements MUST have meaningful alternative text (via the `<title>` element).

The rules for writing this text are the same as for an `<img>`'s `alt` text.

Additionally, the `<title>` element has to be the first child of its parent element for compatibility with SVG 1.1.

`<svg>`s can have multiple containers or groupings of graphical elements inside, each one with its own `<title>`.

### Good example

The following is listed as a good example even though the title text repeats a text element of the SVG itself:

```svg

<svg width="200" height="163" role="img">
    <title>I am text in a circle</title>
    <circle cx="81" cy="85" r="75" fill="#00a" stroke="#000" stroke-width="1"/>
    <text id="text" x="81" y="85" font-size="8px" text-anchor="middle" fill="#fff">
        I am text in a circle
    </text>
</svg>
```

## The alternative text (`<title>`) of an `<svg>` element MUST be programmatically associated with the `<svg>` element via aria-labelledby.

This is because not all screen readers use the title for this purpose. adding `aria-labelledby` with the title's ID
makes it work correctly in basically all cases.

### Good Example

```svg

<svg role="img" aria-labelledby="widgetSales">
    <title id="widgetSales">Total Widgets Purchased during 2016</title>
</svg>
```

## All text within the image that needs to be spoken by a screen reader MUST be associated with the `<svg>` element using aria-labelledby

If the SVG contains other text that should be spoken by a screen reader (not already included in the `<title>`
or `<desc>` elements), it must be associated using `aria-labelledby`

### Good Example

In this example, the svg's `aria-labelledby` attribute lists multiple element IDs separated by spaces.

<svg version="1.1" id="instance3" class="chart" width="490" height="280" aria-labelledby="title3 desc3 jan3 feb3 mar3 apr3 may3 jun3 jul3 aug3 sep3 oct3 nov3 dec3" role="img">
  <title id="title3">Total Widgets Purchased during 2016</title>
  <desc id="desc3">The graph displays the total number of widgets purchased from The ABC Store during 2016, displayed by month.</desc>
  <g>
    <line x1="22" y1="40" x2="470" y2="40" style="stroke: rgb(100, 100, 100); stroke-width: 0.25px; --darkreader-inline-stroke: #a9a196;" data-darkreader-inline-stroke=""></line>
    <line x1="22" y1="90" x2="470" y2="90" style="stroke: rgb(100, 100, 100); stroke-width: 0.25px; --darkreader-inline-stroke: #a9a196;" data-darkreader-inline-stroke=""></line>
    <line x1="22" y1="140" x2="470" y2="140" style="stroke: rgb(100, 100, 100); stroke-width: 0.25px; --darkreader-inline-stroke: #a9a196;" data-darkreader-inline-stroke=""></line>
    <line x1="22" y1="190" x2="470" y2="190" style="stroke: rgb(100, 100, 100); stroke-width: 0.25px; --darkreader-inline-stroke: #a9a196;" data-darkreader-inline-stroke=""></line>
  </g>
  <g id="graphCaption3" role="heading">
     <text x="110" y="30" fill="#009" style="--darkreader-inline-fill: #70a4ff;" data-darkreader-inline-fill="">Total Widgets Purchased during 2016</text>
  </g>
  <g id="jan3" class="bar labels x-labels">
    <rect x="25" y="195" width="33" height="45" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="32" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Jan.</text>
   <text x="33" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">45</text>
  </g> 
  <g id="feb3" class="bar labels x-labels">
    <rect x="62" y="160" width="33" height="80" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="70" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Feb.</text>
   <text x="71" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">80</text>
  </g> 
  <g id="mar3" class="bar labels x-labels">
    <rect x="99" y="140" width="33" height="100" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="107" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Mar.</text>
   <text x="103" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">100</text>
  </g> 
  <g id="apr3" class="bar labels x-labels">
    <rect x="136" y="170" width="33" height="70" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="144" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Apr.</text>
   <text x="145" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">70</text>
  </g> 
  <g id="may3" class="bar labels x-labels">
    <rect x="173" y="140" width="33" height="100" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="181" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">May</text>
   <text x="177" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">100</text>
  </g> 
  <g id="jun3" class="bar labels x-labels">
    <rect x="210" y="130" width="33" height="110" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="218" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Jun.</text>
   <text x="214" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">110</text>
  </g> 
  <g id="jul3" class="bar labels x-labels">
    <rect x="247" y="135" width="33" height="105" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="255" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Jul.</text>
   <text x="250" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">105</text>
  </g> 
  <g id="aug3" class="bar labels x-labels">
    <rect x="284" y="95" width="33" height="145" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="291" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Aug.</text>
   <text x="287" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">145</text>
  </g> 
  <g id="sep3" class="bar labels x-labels">
    <rect x="321" y="100" width="33" height="140" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="329" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Sep.</text>
   <text x="325" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">140</text>
  </g> 
  <g id="oct3" class="bar labels x-labels">
    <rect x="358" y="80" width="33" height="160" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="366" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Oct.</text>
   <text x="362" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">160</text>
  </g> 
  <g id="nov3" class="bar labels x-labels">
    <rect x="395" y="75" width="33" height="165" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="403" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Nov.</text>
   <text x="399" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">165</text>
  </g> 
  <g id="dec3" class="bar labels x-labels">
    <rect x="432" y="60" width="33" height="180" fill="#111" style="--darkreader-inline-fill: #0d0e0e;" data-darkreader-inline-fill=""></rect>
   <text x="440" y="260" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">Dec.</text>
   <text x="436" y="220" fill="#fff" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">180</text>
  </g> 
  <g class="grid x-grid">
    <line x1="22" y1="242" x2="22" y2="10" style="stroke: rgb(100, 122, 122); stroke-width: 0.5px; --darkreader-inline-stroke: #a29a8e;" data-darkreader-inline-stroke=""></line>
    <line x1="22" y1="242" x2="470" y2="242" style="stroke: rgb(100, 122, 122); stroke-width: 0.5px; --darkreader-inline-stroke: #a29a8e;" data-darkreader-inline-stroke=""></line>
  </g> 
  <g class="labels y-labels">
   <text x="15" y="240" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">0</text>
   <text x="10" y="190" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">50</text>
   <text x="5" y="140" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">100</text>
   <text x="5" y="92" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">150</text>
   <text x="5" y="40" fill="#000" style="--darkreader-inline-fill: #e8e6e3;" data-darkreader-inline-fill="">200</text>
  </g> 

</svg>

```svg

<svg role="img"
     aria-labelledby="title desc jan feb mar apr may jun jul aug sep oct nov dec">

    <!-- note that aria-labelledby references the IDs of elements. Screen readers read the text inside those elements, not the IDs themselves, which are used only to identify the elements. -->

    <title id="title">Total Widgets Purchased during 2016</title>
    <desc id="desc">
        The graph displays the total number of widgets purchased from The ABC Store
        during 2016, displayed by month.
    </desc>
    ... (a section of markup was omitted here for brevity)
    <g id="jan" class="bar labels x-labels">
        <rect x="25" y="195" width="33" height="45" fill="#111"></rect>
        <text x="32" y="260" fill="#000">Jan.</text>
        <text x="33" y="220" fill="#fff">45</text>
    </g>
    <g id="feb" class="bar labels x-labels">
        <rect x="62" y="160" width="33" height="80" fill="#111"></rect>
        <text x="70" y="260" fill="#000">Feb.</text>
        <text x="71" y="220" fill="#fff">80</text>
    </g>
    <g id="mar" class="bar labels x-labels">
        <rect x="99" y="140" width="33" height="100" fill="#111"></rect>
        <text x="107" y="260" fill="#000">Mar.</text>
        <text x="103" y="220" fill="#fff">100</text>
    </g>
    ... (partial code sample)
</svg>
```

## The total number of characters of alt text associated with the `<svg>` element SHOULD NOT exceed 150 characters

As with alt text, this is because screen readers read it start to finish with not opportunity to pause or seek within the text.

This rule applies to the `<title>`s, `<desc>`, and other text as a group. 150 characters total for all text in the SVG. If you need more, you do the same thing as with an `<img>` tag - put it in the document body or link to it.