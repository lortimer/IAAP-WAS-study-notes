# Guidelines
Guidelines that spell out technical specs for accessibility

## Web Content Accessibility Guidelines (WCAG)
Published by the World Wide Web Consortium (W3C). Current version is WCAG 2.1 published in 2018. 2.0 was published in 2008.

- [WCAG 2.1 Specification](https://www.w3.org/TR/WCAG21/)
- [What's New in WCAG 2.1](https://www.w3.org/WAI/standards-guidelines/wcag/new-in-21/)
- [WCAG 2.1 Quick Reference](https://www.w3.org/WAI/WCAG21/quickref/)

### Levels
Each criterion in WCAG is designated A, AA, or AAA. Each includes all of the previous.
  - A: Lowest level
  - AA: Used by most orgs as internal standard. Achievable and meaningful.
  - AAA: Highest level. Often only needed for special circumstances. Don't ignore.

### The 4 Main Principles (POUR) and their 13 Guidelines

**1. Perceivable**: information can be perceived. Usually this means it's available as text
  - 1.1 Provide text alternatives for any non-text content so that it can be changed into other forms people need, such as large print, braille, speech, symbols or simpler language.
  - 1.2 Provide alternatives for time-based media.
  - 1.3 Create content that can be presented in different ways (for example simpler layout) without losing information or structure.
  - 1.4 Make it easier for users to see and hear content including separating foreground from background.
  
**2. Operable**: User interface components can be operated. Make sure accessible to keyboard, no keyboard traps.
  - 2.1 Make all functionality available from a keyboard.
  - 2.2 Provide users enough time to read and use content.
  - 2.3 Do not design content in a way that is known to cause seizures.
  - 2.4 Provide ways to help users navigate, find content, and determine where they are.
  - 2.5 Make it easier for users to operate functionality through various inputs beyond keyboard.

**3. Understandable**: Information can be understood. Not too complex or convoluted.
    - 3.1 Make text content readable and understandable.
    - 3.2 Make Web pages appear and operate in predictable ways.
    - 3.3 Help users avoid and correct mistakes.

**4. Robust**: Can be interpreted by wide variety of user agents including assistive technologies like screen readers. Resistant to error. When errors occur, there is good information about how to get around it.
    - 4.1 Maximize compatibility with current and future user agents, including assistive technologies.

### Success Criteria and Conformance Levels
Each WCAG guideline has at least one success criterion - basically a test so you can know if you met it or not. For example, 1.1 Text Alternatives has 1.1.1 Non-text Content, which lays out a set of rules for specific types of components.

### "Sufficient Techniques" and "Advisory Techniques"
Techniques are to Guidelines as Implementation is to a User Story. WCAG lists techniques so developers know how to meet the guidelines.
- Sufficient techniques are mandatory to pass a success criterion
- Advisory Techniques are best practices but not required.

## Authoring Tool Accessibility Guidelines (ATAG) 2.0
Published by the World Wide Web Consortium (W3C). Guidelines for web authoring tools like Dreamweaver, SharePoint, and Webstorm. Goal is to make these tools accessible themselves, and to facilitate the creation of accessible web content. An example is when Webstorm prompts you to add alt text for an image, or label an input element.

- [ATAG 2.0 Overview](https://www.w3.org/WAI/intro/atag.php)
- [ATAG 2.0 Specification](https://www.w3.org/TR/ATAG20/)
- [Implementing ATAG 2.0](https://www.w3.org/TR/IMPLEMENTING-ATAG20/)
- [Essential Components of Web Accessibility (how WCAG and ATAG are inter-related)](https://www.w3.org/WAI/intro/components.php)


These guidelines apply to any website that allows users to create web content - Google Drive tools, Drupal, Wordpress, Blogger, etc.

### Part A. Making the Authoring Tool Accessible
- A.1. Authoring tool user interfaces follow applicable accessibility guidelines
    - A.1.1.  Ensure that web-based functionality is accessible
    - A.1.2.  Ensure that non-web-based functionality is accessible
- A.2. Editing-views are perceivable
    - A.2.1.  Make alternative content available to authors
    - A.2.2.  Ensure that editing-view presentation can be programmatically determined
- A.3. Editing-views are operable
    - A.3.1.  Provide keyboard access to authoring features
    - A.3.2.  Provide authors with enough time
    - A.3.3.  Help authors avoid flashing that could cause seizures
    - A.3.4.  Enhance navigation and editing via content structure
    - A.3.5.  Provide text search of the content
    - A.3.6.  Manage preference settings
    - A.3.7.  Ensure that previews are at least as accessible as in-market user agents
- A.4. Editing-views are understandable
    - A.4.1.  Help authors avoid and correct mistakes
    - A.4.2.  Document the user interface, including all accessibility features

### Part B. Support the production of accessible content
- B.1. Fully automatic processes produce accessible content
    - B.1.1. Ensure that automatically-specified content is accessible
    - B.1.2. Ensure that accessibility information is preserved
- B.2. Authors are supported in producing accessible content
    - B.2.1. Ensure that accessible content production is possible
    - B.2.2. Guide authors to produce accessible content
    - B.2.3. Assist authors with managing alternative content for non-text content
    - B.2.4. Assist authors with accessible templates
    - B.2.5. Assist authors with accessible pre-authored content
- B.3. Authors are supported in improving the accessibility of existing content
    - B.3.1. Assist authors in checking for accessibility problems
    - B.3.2. Assist authors in repairing accessibility problems
- B.4. Authoring tools promote and integrate their accessibility features
    - B.4.1. Ensure the availability of features that support the production of accessible content
    - B.4.2. Ensure that documentation promotes the production of accessible content

## Web Accessibility Initiative Accessible Rich Internet Applications (WAI-ARIA) 1.0

- [WAI-ARIA Overview](http://www.w3.org/WAI/intro/aria.php)
- [WAI-ARIA 1.0](http://www.w3.org/TR/wai-aria/)
- [WAI-ARIA Authoring Practices 1.1](https://www.w3.org/TR/wai-aria-practices-1.1/): This is one of the best places to learn how to implement ARIA

ARIA is intended to fill the gaps between the accessibility features of HTML and the needs of modern, dynamic web apps, especially with regard to JavaScript.

ARIA is almost entirely for screen readers, although some of it is for speech-recognition users and keyboard-only users. ARIA allows augmentative tools to know what's happening visually on the screen.

Things a screen-reader user can't see:

- If a link opens a popup window
- If an object (like a folder icon) is expandable
- If an object is currently expanded or collapsed
- If something has changed or been updated on the page (via "live regions")
- What type of object or widget it is; for example:
    - A tab panel
    - A tab
    - A slider
    - An alert dialog
    - A tooltip
    - A menu
    - A menu item
    - A hierarchical tree view
    - And several other pre-defined roles
