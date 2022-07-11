# Color

We canot use color as the only way we convey information. "Information" here means conveying meaning, as in emphasizing text, distinguishing visual elements from each other, distinguishing dynamic and static elements, and anything else the user is meant to perceive and understand.

**Color choice can be disabling.** Some people may have pain when looking at bright lights, like a white background on a screen.

## Color that Conveys Meaning

### Any information conveyed by color MUST be accompanied by a programmatically determinable text alternative

Examples include:
- Buttons or other UI elements that look the same other than color
- Color-coded routes on a map
- Highlighting text with color to convey a meaning - this is why links also have an underline.

Essentially, anything color-coded has to have a text-based way to understand the code.

#### Good Example: Table

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

#### Example: Highlighting form errors

If a user forgets to fill out a form field, it is common to highlight that field and display a generic error message like "Please fill out all required fields".

If we only use highlighting, many users won't be able to see it. We need to use specific text, like "Please fill out the email field".

### The text alternative for information conveyed by color MUST accurately convey the same information without color

The example is a bar chart where the bars below a specific value are red and the other bars are blue. The good example has alt text pointing out the bars that are red and why.

I would argue that that's better for the chart's long description, and a more illustrative example is highlighting the red bars in a different way.

### Any information conveyed by color MUST be accompanied by a visible alternative (text, image, etc.) that does not depend on color for meaning

This seems to be based on distinguishing things from one another rather than conveying information. The example is a pie graph with lots of similar colors in it. The better example has the labels laid out with each pie slice instead of in a legend.

The distance from the legend to the pie slices matters also because people who enlarge the screen have to move back and forth between the legend and the chart.

## Color to Distinguish Links from Text

### Color alone MUST NOT be used to distinguish links from surrounding text unless the color contrast between the link and the surrounding text is at least 3:1 and an additional differentiation (e.g. underline, outline, etc.) is provided when the link is hovered or receives focus

Note, this requires contrast between link text and non-link text. Achieving 3:1 contrast between those colors AND between both colors and the background seems damn near impossible.

Solutions:
- Different color plus underline (the default)
- Different color plus underline the links only on hover and focus
    - This is discouraged, especially in the main body of the document where it is surrounded by non-link text.
- Different background color on hover and focus
- Add and ooutline or border on hover and focus
- Placement in a navigation menu
    - Sighted users understand that items are clickable if the menu is styled in a way that makes it obvious. This is a little subjective, but should be consistent with contemporary design trends.

It's important not to rely only on hover styling to distinguish a link. Users should be able to identify a link just by looking at it.

## Color to Distinguish UI Components

### Color SHOULD NOT be used as the sole method of distinguishing UI components and/or their surrounding content, unless the color contrast between the UI components and/or surrounding content is at least 3:1

The bad example used is 4 lines of text, each with an icon next to it. The first 2 are not buttons, the second 2 are buttons. The only distinguishing feature is that the buttons have blue text - no hover state, no outline, etc.

Ways to make it better:
- Change background color of buttons
- Give the buttons an outline
- Other styling to distinguish buttons from text.

## Allowing Customizability

### Visible text SHOULD be standard text in the markup (not images or graphic versions of text), to allow user customization of text color and contrast

Essentially, using text in markup rather than images of text means users can customize the colors.

### Visible UI components SHOULD use native controls and features (not images or graphic versions of controls) where available, to allow user customization of interface color and contrast

Don't make a PNG of a button with text on it and use `<img role="button" />`. Use native controls with real text in them.