# The Challenge of User-Generated Content

User-generated content will necessarily be inaccessible. Strategies:

- Automate accessibility fixes - Very difficult
- Limit what users can post - templates
- Prompt the user with guides - IDE suggestions
- Audit tools
- The authoring tool itself must be accessible

There's a whole set of guidelines for Authoring tool accessibility: [ATAG](https://www.w3.org/TR/ATAG20/)

## ATAG

Any web app that allows user input that is posted to the web is an Authoring Tool. Examples:
- CMS and Blog systems
- User comments
- Product rating and review
- Social Media
- Document review and collaboration

ATAG has 2 parts
1. Make the authoring tool user interface accessible (Mostly just WCAG)
2. Support the production of accessible content.

### The major points

#### Fully automatic processes produce accessible content

1. Ensure that automatically-specified content (templates) is accessible
2. Ensure accessibility information is preserved when filtering content

#### Authors are supported in producing accessible content

1. Ensure that Accessible content production is possible

You can do this by creating authoring widgets that have built-in accessibility features, like Webstorm, or allow authors to customize the HTML source of their content.

You can't expect most users to generate their own accessible content. You have to enforce accessibility features for the types of content people generate

2. Guide Authors to produce accessible content.

Wizard interface, or a diagram or other explanation of the accessibility features they are adding

3. Assist authors in managing alternative content for non-text content

Reusable content retains its accessibility info, and should be editable per instance

4. Assist authors with accessible templates

Obviously, the built-in templates must be accessible. Allow users to create their own accessible templates. If any are inaccessible, warn users about that and push them toward the accessible ones

5. Assist authors with accessible pre-authored content

#### Authors are supported in improving the accessibilty of existing content

1. Assist authors in checking for accessibility problems - Automated checker tool
2. Assist authors in repairing accessibility problems. Provide general information and tools

#### Authoring tools promote and integrate their accessibility features

1. Ensure the availability of features that support the production of accessible content
   1. Accessibility features should be a natural part of the flow of the tools, not bolted on or hidden
   2. Prominent
   3. Turned on by default
   4. Warn users if they are allowed to turn the features off
2. Ensure that documentation promotes the production of accessible content
   1. Documentation for authoring content in general includes accessibility features

## Automated Solutions to make Inaccessible content Accessible

Machine Learning and other tech has made some pretty good solutions recently:
- Skype Translator converts speech to text, then translates the text to another language. A Good by-product of this is the text-to-speech, allowing deaf people to use Skype.
- Automatic captions on YouTube videos uses voice-recognition on the audio and synchronizes captions with the video. Limitations:
  - The voice must be clear
  - Good sound quality
  - No overlapping voices
  - No significant interference from background sound or music
  - Accents and language must be familiar to YouTube's algorithm
  - Doesn't include audio description
- Automated alt text on Facebook images began in 2016 and works, but is limited
  - Descriptions are short and general - don't match specific context of the image
  - Don't identify people (privacy concerns)
  - May not turn images of text into text
  - Facebook doesn't allow you to add alt text yourself or correct their guess.
    - The description field is not used to actually describe the image in an accessible way

### The future of automated accessibility

- Automated table structures
- Automated labelling of form fields
- Automated ARIA widget correction
- Automated image contrast correction

Automated solutions can be applied during authoring or on the end result.