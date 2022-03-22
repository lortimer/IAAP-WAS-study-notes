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

Deafblind users benefit from the same techniques as blind users because they also use screen readers. The difference is that they often use a refreshable braille device instead of software to read the text on the screen.

### Everything must be in a text format

There are no exceptions, but many nuances:

- The alt text for images counts as text.
- Labels, including invisible labels like aria-label count as text, as long as the elements are not hidden from screen readers via aria-hidden="true".
- ARIA live announcements, whether visible on screen or not, count as text.
- It can be acceptable under some uncommon circumstances to add visually-hidden text just for screen reader users via the CSS clip method, but this method should be used only as a last resort.
- Synchronized captions in videos DO NOT count as text for the deafblind user. Some braille displays can read them, but they change too quickly.
  - A transcript is the only solution

### Multimedia for deafblind audiences

No such thing. Text transcript is the only way. It should be easy to find and be identified as a transcript. Typical methods:
- In regular paragraphs on the page
  - If it's long, can be in a scrollable container
  - Use a "skip transcript" link like a skip-nav link.
- In a dialog, activated with a "Show transcript" button
- On a separate page with a "Go to transcript" link.

HTML doesn't have a native way to associate a transcript to a video even though there is a native way to associate captions with a video using the `<track>` element.

Don't use `aria-describedby` to associate a transcript - it is read before the focus lands on the video. This text can't be paused or navigated through.

### Ideal design for deafblind users

- Text-first design: Multimedia is useless to this audience.
- Simple: navigation and comprehension is easier
- Semantic Structure: landmarks, headings, links, form elements, etc. Group things logically
- Timing Control: braille is slow to read. Give users control over timing - including extending time limits and avoiding session timeouts.
- Common wording: Makes navigation easier by allowing people to search the page for expected things. For example "Contact us" and "about us" are great, "get a hold of us" and "who we are" are not as common.
- Screen reader techniques.

## Deaf: A Silent Visual UX