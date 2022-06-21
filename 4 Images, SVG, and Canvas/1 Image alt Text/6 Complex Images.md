## Complex Images

An example of a complex image with a necessarily long description would be a bar graph. The purpose of the graph is to convey a lot of information, but you couldn't fit it all in the alt text.

## Complex images MUST be briefly described using alt text AND MUST have a more complete long description

The alt text for a bar graph would briefly describe the graph, and the full description would go somewhere else in the document.

There are a few ways of achieving this:

- Provide the long description in the context of the HTML document itself.
- Provide a button that expands a collapsed region that contains the long description.
- Provide a button to open a dialog that contains the long description.
- Provide a link to a long description on another page via a normal link text.

### Good example - bar graph

Notice that the alt text points the user to the text below and doesn't waste any words describing it beyond what it is and what it contains.

```html
<img class="border" src="bar-chart.png" width="546" height="330" 
alt="Bar chart with percentages. Extended description below chart."
aria-describedby="description-extended">

<div id="description-extended">
    <p>Last year, Josephine kept track of the number of times she saw squirrels outside of the window while eating meals. She took this data and calculated the overall relative yearly percentage of meals with squirrel sightings on a monthly basis. The monthly proportion, or percentage, of squirrel sightings during meals over the course of the year is as follows:</p>
    <ul>
        <li>January: 14%</li>
        <li>February: 10%</li>
        <li>March: 9%</li>
        <li>April: 18%</li>
        <li>May: 3%</li>
        <li>June: 1%</li>
        <li>July: 20%</li>
        <li>August: 14%</li>
        <li>September: 5%</li>
        <li>October: 1%</li>
        <li>November: 3%</li>
        <li>December: 2%</li>
    </ul>
    <p>Josephine apparently has more time on her hands to keep track of this kind of thing than the rest of us.</p>
</div>
```

## The long description (or a link or button to access the long description) SHOULD be visible to sighted users

To allow the long description to help anyone, it should be visible to sighted users. People with cognitive disabilities, or who can process the meaning better by reading prose will benefit.

This is another reason NOT to put the long description in alt text where it is hidden from sighted users.

## The long description SHOULD be programmatically associated with the image

Using `aria-describedby`! As in the good example above.