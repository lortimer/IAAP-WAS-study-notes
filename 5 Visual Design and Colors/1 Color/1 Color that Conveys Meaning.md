# Color that Conveys Meaning

## Any information conveyed by color MUST be accompanied by a programmatically determinable text alternative

Examples include:
- Buttons or other UI elements that look the same other than color
- Color-coded routes on a map
- Highlighting text with color to convey a meaning - this is why links also have an underline.

Essentially, anything color-coded has to have a text-based way to understand the code.

### Good Example: Table

In the table below, the level column uses color and text to convey the level of each course.

```html
<tbody><tr>
    <th scope="col" style="width:200px">Course
      Title</th>
    <th scope="col" style="width:85px">Level</th>
  </tr>
  <tr>
    <td>String Theory</td>
    <td style="background: rgb(184, 59, 59) none repeat scroll 0% 0%; color: white; text-align: center; --darkreader-inline-bgcolor: #932f2f; --darkreader-inline-bgimage: none; --darkreader-inline-color: #e8e6e3;" data-darkreader-inline-bgcolor="" data-darkreader-inline-bgimage="" data-darkreader-inline-color="">Advanced</td>
  </tr>
  <tr>
    <td>Quantum Mechanics</td>
    <td style="background: rgb(184, 59, 59) none repeat scroll 0% 0%; color: white; text-align: center; --darkreader-inline-bgcolor: #932f2f; --darkreader-inline-bgimage: none; --darkreader-inline-color: #e8e6e3;" data-darkreader-inline-bgcolor="" data-darkreader-inline-bgimage="" data-darkreader-inline-color="">Advanced</td>
  </tr>
  <tr>
    <td>Basic Sewing and Stitching</td>
    <td style="background: rgb(255, 255, 0) none repeat scroll 0% 0%; text-align: center; --darkreader-inline-bgcolor: #999900; --darkreader-inline-bgimage: none;" data-darkreader-inline-bgcolor="" data-darkreader-inline-bgimage="">Intermediate</td>
  </tr>
  <tr>
    <td>How to Tie your Shoe</td>
    <td style="background: rgb(0, 128, 0) none repeat scroll 0% 0%; color: white; text-align: center; --darkreader-inline-bgcolor: #006600; --darkreader-inline-bgimage: none; --darkreader-inline-color: #e8e6e3;" data-darkreader-inline-bgcolor="" data-darkreader-inline-bgimage="" data-darkreader-inline-color="">Beginner</td>
  </tr>
</tbody>
```

It could also use icons or images instead of text, as long as those icons had a text alternative.

### Example: Highlighting form errors

If a user forgets to fill out a form field, it is common to highlight that field and display a generic error message like "Please fill out all required fields".

If we only use highlighting, many users won't be able to see it. We need to use specific text, like "Please fill out the email field".

## The text alternative for information conveyed by color MUST accurately convey the same information without color

The example is a bar chart where the bars below a specific value are red and the other bars are blue. The good example has alt text pointing out the bars that are red and why.

I would argue that that's better for the chart's long description, and a more illustrative example is highlighting the red bars in a different way.

## Any information conveyed by color MUST be accompanied by a visible alternative (text, image, etc.) that does not depend on color for meaning

This seems to be based on distinguishing things from one another rather than conveying information. The example is a pie graph with lots of similar colors in it. The better example has the labels laid out with each pie slice instead of in a legend.

The distance from the legend to the pie slices matters also because people who enlarge the screen have to move back and forth between the legend and the chart.

The example is a pi