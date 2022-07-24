# Characteristics of Screen Readers

## No Visual Interface

### Screen readers interact invisibly with other software

For the most part, they interact invisibly with other software. They usually have a configuration menu that is visible.

### You must use keyboard shortcuts

They offer many keyborad shortcuts, but each has a core set of them. They are best learned by using the software.

### Some screen readers have visual aids

For instance, a border on the currently-focused item. This can make up for a lack of accessibility features on a website.

Voiceover on MacOS shows captions of what the screen reader is saying, which is convenient for using it in a place where you have to be quiet.

## No Mouse, Just Keyboard

There are very few exceptions to this rule. Screen reader users use a keyboard and no mouse. People with low vision or reading disabilities may use a mouse.

### Everything must be keyboard-accessible

- Users must be able to tab to all controls (links, buttons, form elements, etc.).
- Users must be able to activate all links with the enter key.
- Users must be able to activate all buttons with the enter key and the space bar.
- Mouse hover features must have equivalent keyboard event handlers.
- When items are hidden from sighted users (such as drop-down menus), users must not be able to tab to the hidden items (they must be unavailable to the keyboard until activated by the user or by the script).
- When a popup dialog appears, the keyboard focus must go to the dialog. When the dialog closes, the focus must go back to the original control that activated it (or to another logical location if that control is no longer available or is not the best location).
- Custom JavaScript widgets should adhere to the ARIA Authoring Practices opens in a new window for keyboard behaviors.
- Pages must not have any keyboard traps (users must be able to get into and out of all JavaScript widgets).
- The tab order through controls must be logical.


## Linear Content

### The reading order is the DOM order
### Screen readers require a logical linear reading order in the DOM

## Non-Linear Navigation

### Screen readers allow users to navigate to headings, landmarks, and other features
### Screen readers require structural and semantic markup

## No Visual Styles

### Screen readers ignore almost all CSS styles
Screen reader users can customize their settings to hear some style information, but they are usually unaware of:

- Color
- Background color
- Background images
- Font size
- Font style
- Bold
- Italic
- All capitals (unless the user listens to the word character by character)
- Visual position
- Visual spacing between items
- Columns or floating containers

### Screen readers hide content marked as display:none

This is one CSS property they do respsect. Users can't hear or interact with elements that have this property.

## Pronunciation

### Mispronunciations

Screen readers do a pretty good job pronouncing words. They can have trouble with homographs, words written the same way with different pronunciations.

DO NOT misspell things on purpose to force a screen reader to pronounce it some specific way. Users can listen to words over and over or hear the spelling.

### User customization of pronunciation

Some screen readers allow customization of pronunciation. This is out of your control as an author.

### Characters & Symbols

### Screen reader default settings generally read only some punctuation

Generally, they don't read commas and periods, they just pause briefly as a speaker does. There is more variation in characters like hyphen, parentheses, or semicolon, and it can be customized.

### Screen reader default settings generally read only a few symbols

They usually do not read most non-alphanumeric symbols. The safest ones to use are:

- @ (the at symbol)
- & (ampersand, written either as & or &amp; in the markup)
- / (slash)
- © (copyright, written as &copy;)
- ® (registered, written as &reg;)
- ™ (trademark, written as &trade;)
- ¶ (paragraph, written as &para;)
- • (bullet, written as &#8226;)
- $ (dollar)
- € (Euro, written as &#8364;)
- £ (British pound, written as &pound;)
- ¥ (Yen, written as &yen;)
- % (percent)
- ½ (one half, written as &frac12;)
- ¼ (one fourth, written as &frac14;)
- ¾ (three fourths, written as &frac34;)
- ° (degrees, written as &deg;)

### Screen readers allow customization of character and symbol "verbosity"

This can range from reading all punctuation to reading none. There is no standardized user experience when it comes to reading symbols. Most users don't change the settings, so testing with default settings is good. Be aware that the meaning can be lost if symbols are very important and must be read.

## Abbreviations & Acronyms

### How screen readers treat abbreviations

#### Pronounceable abbreviations

Screen readers generally try to pronounce acronums and nonsensical words is they have sufficient vowels and consonants to be pronounceable. Otherwise they spell out the letters. NASA is pronounced as a word, DHS is pronounced as three letters.

#### Unpronounceable abbreviations

If a user doesn't understand a word they can have it repeated or read letter by letter. Screen readers distinguish upper and lower case letters using pitch.

### Expand the first instance of an abbreviation

On any page, just do it. Then there's much less confusion about what it means. It doesn't hurt anyone.

### Semantic markup for abbreviations

```html
<abbr title="Self-Contained Underwater Breathing Apparatus">SCUBA</abbr>
```

Some screen readers will read the expanded version of the abbreviation, others do not. This is a setting users can change on most.

## Screen Readers Read the Accessibility API and/or DOM

They **don't** read the raw HTML source. They read the content after parsing by the browser, meaning after Javascript and styles have been applied.

## Virtual Buffer

### Screen readers create a copy of the web page

The screen reader creates an in-memory copy of the DOM and updates it as the DOM changes, but there can be a delay in updating the copy. It's usually fractions of a second, but that can also affect your javascript.

You have to wait some time when new content appears before sending it focus or you risk focusing a non-existant or empty element. The recommendation is 0.5 to 1 seconds, at least when an AJAX request has finished. Mobile devices require more like 2 seconds because they have less CPU.