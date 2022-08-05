# Other Testing Methodology Part 1

## Test for Meaning Conveyed with Color

1. First, identify any instances on the web page where color is being used to convey meaning.
2. If there are instances, check that an equivalent text-based method is used as well to convey meaning.
3. Additionally, evaluate the content and information presented on the web page, and check if there are any references to colors in the text-based content (e.g., instructions that tell users to select a green button).

## Test Alt Text Quality

Good Alt text is:
- Concise
- Descriptive of the purpose of the image
  - What an icon button does
  - Conveys the context the author intended, not merely a description

Background images need to have alternative text on the page if it is useful, and an automated test won't catch that.

Below is a table of the common types of images and a general approach to creating alt text for them.

| Image Type                                   | Alt Text Considerations                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Active (or Actionable)                       | Alternative text should describe the functionality of the image or the destination if the image is used as a link.                                                                                                                                                                                                                                                                                                                                                        |
 | Informative and Informative Background (CSS) | Alternative text should describe the purpose of the image, convey information in the image that allows users to understand how it contributes to web page content.                                                                                                                                                                                                                                                                                                        |
 | Decorative                                   | If the image is purely decorative, there should be no text alternative. Keep in mind, if the image is provided using an <img> tag it still needs an alt attribute, but the value should be empty (or null) so assistive technologies will ignore the image (in code, it looks like alt="").                                                                                                                                                                               |
 | Redundant                                    | If an image is right next to actual text that describes the image, alternative text should not be provided. It will just repeat the description that is provided in the text next to it. Again, if the image is provided using an <img> tag it still needs an alt attribute, but the value should be empty (or null).                                                                                                                                                     |
 | Complex (e.g., Charts, Graphs)               | Complex images need both alternative text and a long description. Since alternative text is supposed to be brief, an extended description needs to be provided to convey all the information presented in a complex image. The long description should be easy to locate and should be an equivalent substitute of information within the image. Presenting the information in a different format, such as a data table, is an acceptable substitute for a complex image. |
 | Input                                        | Alternative text should be an accurate description of the form input, control, or button; but the alternative text should not include the role of the input, control, or button. For instance, alternative text for a Submit button should say "Submit", not "Submit button". If the alternative text includes the role, the role may be rendered twice to those using assistive technologies like a screen reader.                                                       |
 | Canvas                                       | Meaningful alternative text for `<canvas>` images should be provided either through the aria-label or aria-labelledby attribute. For complex `<canvas>` images, additional description should be available through an aria-describedby ID reference to text in the DOM.                                                                                                                                                                                                   |

### Testing Methodology

You should use a screen reader since alt text isn't visible.

Background images can't be focused, and therefore won't be read or even found by a screen reader.

- Alternative text exists: Every image has appropriate alternative text.
- Alternative text is descriptive: The alternative text should describe the purpose of the image in a way that adequately substitutes for the image.
- Alternative text is concise: Alternative text should be brief. There is no official limit, but a limit of approximately 150 characters is considered best practice.
- Long description exists for complex images: The long description is on the same page, near the complex image, or available in a link to another page.
- Long description is an adequate substitute for the image: Someone who cannot see the image should be able to make sense of it and understand the purpose of the image based on the long description.

