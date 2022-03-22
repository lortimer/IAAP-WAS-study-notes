# User Experiences for Various types of disability

## Blind: An Audio-Structural UX

People who are blind listen to screen readers read web pages aloud, but not from top to bottom. They can navigate the page's structure in many ways, including by types of elements.

Interactive components require more sophisticated ways of presenting the semantic information. Most important is to present the name, role, and properties of each element, and to update the values when they change, like when a region is collapsed or expanded.

### Audio-Structural Page UX

It would be a waste of time to listen to everything on a web page every time

#### How does a user explore a web page?

Screen readers can provide a count of the type of elements on a page, for example: "page has 4 regions, 12 headings, and 78 links".

Then, users can hear a list of just one type, if they'd like. The list could include the following types:
- Anchors (links)
- Block quotes
- Buttons
- Checkboxes
- Controls (selectable ARIA widget controls, e.g. tabs in a tablist)
- Divisions
- Edit boxes (text inputs)
- Form fields
- Frames
- Graphics
- Headings
- Links
- List items
- Lists
- Objects
- Paragraphs
- Placemarkers
- Radio buttons
- Tables

The user can also navigate by landmarks or regions, like `<nav>`, `<main>`,and `<article>`.

#### Example - Wikipedia Home Page

This is what the Wikipedia homepage read like to a screen reader in Feb. 2017:

- Landmarks (0 total)
    - No landmarks available.
- Headings (1 total)
    - Level 1: "Wikipedia The Free Encyclopedia"
- Form elements (4 total)
    - Text input: "Search"
    - Select list: "English"
    - Button: no label is provided
    - Button: Read Wikipedia in your language
- Images (2 total)
    - "Wikipedia"
    - "Wikipedia logo"
- Links (11 total, in this part of the page)
    - "Wikipedia"
    - "English 5 323 000+ articles"
    - "日本語 1 044 000+ 記事"
    - "Deutsch 2 016 000+ Artikel"
    - "Español 1 306 000+ artículos"
    - "Русский 1 363 000+ статей"
    - "Français 1 829 000+ articles"
    - "Italiano 1 323 000+ voci"
    - "中文 918 000+ 條目"
    - "Português 951 000+ artigos"
    - "Polski 1 201 000+ haseł"
- Lists (0 total, in this part of the page)
    - No lists available.

#### Issues with the Wikipedia Home Page
- There are no landmarks. A user doesn't have the option to navigate by them.
- The search button does not have a label, just a magnifying glass icon that is not read by the screen reader.
- The link text includes the name of the language and the number of articles. There are spaces in the numbers insetad of commas or periods, so the screen reader says "five, three hundred twenty-three, zero zero zero." instead of "five million, three hundred and twenty-three thousand"
- There are no lists, although the list of languages could be styled as a list. This would help the user know how much content is there before diving in.

#### What is the ideal audio-structural experience for a page?

Every site is different, but there are some things to keep in mind
- Short list of landmarks to make navigating by them quick
- Heading tags, only a single h1. Don't skip levels!
- Form inputs have labels
- Alt text on images
- Links
    - Accessible "name"(?)
    - Text should convey its purpose or destination
    - Make sense out of context and unique on the page
- Use correct type of list: `<ul>`, `<ol>`, or `<dl>`

### Audio-Structural Page UX

Screen reader users typically use a keyboard, not a mouse. They listen for feedback as they interact with the page:

- Name: The name or label of the element
- Description: Extra info (from "aria-describedby"). Announced after name, if present.
- Role: What kind of element is it? Announced for most semantic elements.
- Value:
    - Properties: Characteristics of the element, like a min and max value for sliders, "aria-controls", or "aria-owns"
    - States: Changeable conditions about the element. If it's selected, checked, hidden, expanded, etc.
        - Announced automatically when an aria state changes - no code needed.
- "Live" announcements (see below)

#### Live Events

The course describes these as things like live captions on video. I think they mean time-based, possibly non-text-based changes to the pages

Possible solutions:
- "Continuous AJAX updates": changing text on the page as it updates
    - You have to refocus their place on the page when it changes, or notify them somehow, because they won't see when the changes happen.
- "Load more live text": A button to allow users to load more live information as they wish, creating a natural place to change focus.

## Deafblind: A Tactile-Structure Text-only UX
## Deaf: A Silent Visual UX