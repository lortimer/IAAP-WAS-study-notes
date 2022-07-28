# Wayfinding and Reading Content with Screen Readers Part 3

## Graphics

### How screen readers treat images

#### Alt text

`<img src="cat_0123.jpg" alt="A tabby cat playing with a ball of string">`
will be read as "Graphic, a tabby cat playing with a ball of string." There's no need to put "image of" or "graphic of"

#### Missing alt text

Some screen readers use the image file's `src` as the alt text if it is not specified.

#### Null alt text

This means empty alt text, like `<img src="cat.jpg" alt="">`. Screen readers ignore these completely.

#### Linked images

```html
<a href="cat_page.html"><img src="cat_0123.jpg" alt="A tabby cat playing with a ball of string"></a>
```
The screen reader would say "link graphic, a tabby cat playing with a ball of string." for the above example.

#### Linked images missing alt text

Some screen readers read the link destination. 
```html
<a href="cat_page.html"><img src="cat_0123.jpg" alt=""></a>
```
will be read as "Link graphic, cat underscore page dot H T M L"

#### Image map hot spots

JAWS reads the alt text for these, so the alt text should describe the link's destination.

### List all graphics

Only available on JAWS (Insert + Control + G) and VoiceOver on macOS (Control + Option + U to open the rotor, then left/right arrows to select images.)

### Navigate from one graphic to the next

| Screen Reader & Browser               | Command                                                                                                    |
|---------------------------------------|------------------------------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE 	 | G                                                                                                          |
 | NVDA with Firefox, Chrome, Edge       | 	G                                                                                                         |
 | VoiceOver with Safari (iOS)           | 	Rotate two fingers on the screen (like turning a dial) to open the rotor, locate Images, then swipe right |
 | TalkBack with Chrome, Firefox         | 	Not available                                                                                             |
 | VoiceOver with Safari (macOS)         | 	Control + Option + Command + G                                                                            |
 | Narrator with Edge                    | 	Not available                                                                                             |

## Links

### How screen readers treat links

- Unvisited links: Screen readers typically say "link" then read the link text.
- Visited links: If the user has already been to the link destination, some screen readers will say "visited link", followed by the link text. Others will just say "link".

### Good practices for link text

Links Must have link text! If a background image is the only content, include an aria-label or add visually-hidden text.

Link text should be descriptive because it will most likely be read out of the context of the surrounding text.

Don't put the word "link" in the text, screen readers do that.

Use consistent naming of links. Two links with the same destination on the same page should have the same link text. On the other hand, two links with the different destinations on the same page should have different link text.

### List all links

If you're interested only in links, you can do this without the tab key:

| Screen Reader & Browser               | Command                                                                                  |
|---------------------------------------|------------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE 	 | Insert + F7                                                                              |
 | NVDA with Firefox, Chrome, Edge       | 	Insert + F7 (to show Elements List), then choose links                                  |
 | VoiceOver with Safari (iOS)           | 	Not available                                                                           |
 | TalkBack with Chrome, Firefox         | 	Not available                                                                           |
 | VoiceOver with Safari (macOS)         | 	Control + Option + U (to open the Rotor), then use left or right arrows to select links |
 | Narrator with Edge                    | 	Caps Lock + F7                                                                          |

### Navigate from one link to the next

| Screen Reader & Browser             | Command                                                                                                                                 |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE | 	Not available                                                                                                                          |
 | NVDA with Firefox, Chrome, Edge     | 	K                                                                                                                                      |
 | VoiceOver with Safari (iOS)         | 	Use the rotor to select links (twist to fingers on the screen to left or right), then swipe down with one finger                       |
 | TalkBack with Chrome, Firefox       | 	Swipe up then down (or swipe down then up) repeatedly to cycle through the reading controls until "Links" is selected, then swipe down |
 | VoiceOver with Safari (macOS) 	     | Control + Option + Command + L                                                                                                          |
 | Narrator with Edge                  | 	K (in Scan Mode only)                                                                                                                  |

### Navigate unvisited links only

JAWS and NVDA let you do this with the "U" key, others don't.

### Navigate visited links only

JAWS and NVDA let you do this with the "V" key. VoiceOver on macOS uses Control + Option + Command + V. Others don't have this.

## Tables

### How screen readers read tables

When a screen reader announces a table, it says how many columns and rows there are. "Table with 4 columns and 5 rows."

The user can choose to keep reading in regular mode, or navigate cell by cell, called "table navigation mode". In regular mode, it starts in the top left corner and reads each row left to right. In table navigation mode, the user can navigate in any direction reading each cell.

### Show list of all tables

Available only on JAWS (Insert + F3 (to open Elements List), then select tables) and VoiceOver on macOS (Control + Option + U (to open rotor), then use left/right arrows to select tables). 

### Navigate from one table to the next

| Screen Reader & Browser             | Command                                                                                                            |
|-------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE | 	T                                                                                                                 |
 | NVDA with Firefox, Chrome, Edge     | 	T                                                                                                                 |
 | VoiceOver with Safari (iOS) 	       | Use the rotor to select tables (twist two fingers on the screen to left or right), then swipe down with one finger |
 | TalkBack with Chrome, Firefox       | 	Not available                                                                                                     |
 | VoiceOver with Safari (macOS) 	     | Control + Option + Command + T                                                                                     |
 | Narrator with Edge                  | 	T (in Scan Mode only)                                                                                             |

### Navigate between cells within a table

| Screen Reader & Browser               | Command                                |
|---------------------------------------|----------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE 	 | Control + Alt + Arrow keys             |
 | NVDA with Firefox, Chrome, Edge       | 	Control + Alt + Arrow keys            |
 | VoiceOver with Safari (iOS)           | 	Swipe up/down/left/right              |
 | TalkBack with Chrome, Firefox         | 	Swipe left/right and explore by touch |
 | VoiceOver with Safari (macOS)         | 	Control + Option + Arrow keys         |
 | Narrator with Edge 	                  | Control + Alt + Arrow keys             |

### Searching within the Page

## Searching within the Page

| Screen Reader & Browser             | Command                                                         |
|-------------------------------------|-----------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE | 	Control + F                                                    |
 | NVDA with Firefox, Chrome, Edge 	   | Control + F                                                     |
 | VoiceOver with Safari (iOS)         | 	Not available                                                  |
 | TalkBack with Chrome, Firefox       | 	Swipe left then down, or use browser's "Find in page" function |
 | VoiceOver with Safari (macOS)       | 	Control + Option + F                                           |
 | Narrator with Edge                  | 	Control + F                                                    |