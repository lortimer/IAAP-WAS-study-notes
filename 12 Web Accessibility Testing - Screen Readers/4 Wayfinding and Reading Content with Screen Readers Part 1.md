# Wayfinding and Reading Content with Screen Readers Part 1

## Page Title

The page title helps identify tabs when multiple are open. Screen readers typically announce the page title when the page loads. It's the first thing the user hears.

Users expect to hear the same or similar information in the page title and the first heading on the page.

## Read All Content

Screen readers typically read the page title, followed by a summary of the page landmarks and other features, E.G. "Page has 5 frames, 5 regions, 39 headings, and 153 links". After that, it reads the contents of the page in DOM order. If you interrupt the reading you can restart with a shortcut like one of these:

- In JAWS, press Insert + Down arrow.
- In NVDA, press Insert + Down arrow.
- In VoiceOver for macOS, press Control + Option + A.
- In Narrator, press Caps Lock + Down Arrow or Caps Lock + Control + R.
- In TalkBack for Android, triple tap with two fingers. Or open the TalkBack menu by swiping down then right or up then right, then repeatedly swipe right until you reach "Read from next item," then select it by double tapping.

Most people don't listen to most pages from start to finish. It takes a long time and there are ways to listen to only what they're interested in.

## Headings

Screen readers read headings like this: If a heading is `<h3>Ham and Cheese</h3>`, it would say "heading level 3 Ham and Cheese".

Screen reader users usually can't glance at the page to understand its structure, but headings provide a way to get a similar effect.

### List All Headings

| Screen Reader & Browser             | Command                                                                              |
|-------------------------------------|--------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE | 	Insert + F6                                                                         |
 | NVDA with Firefox, Chrome, Edge     | 	Insert + F7 (to open Elements List), then select Headings                           |
 | VoiceOver with Safari (iOS)         | 	Not available                                                                       |
 | TalkBack with Chrome, Firefox       | 	Not available                                                                       |
 | VoiceOver with Safari (macOS)       | 	Control + Option + U (to open rotor), then use left/right arrows to select headings | 
 | Narrator with Edge                  | 	Caps Lock + F6                                                                      |

Below this table, the course shows screenshots of JAWS and NVDA UI menus showing the heading list with options to sort them and filter by heading level. The course previously said screen readers don't have UI for interacting with the page, I'm not sure what they woould consider this UI they're showing me. The NVDA window also has other "tabs" to look at links, inputs, buttons, and landmarks.

Apparently, mobile screen readers cannot do this.

### Navigate from one heading to the next

| Screen Reader & Browser             | Command                                                                                                                                    |
|-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE | 	H                                                                                                                                         |
| NVDA with Firefox, Chrome, Edge     | 	H                                                                                                                                         |
| VoiceOver with Safari (iOS)         | 	Use the rotor to select headings (twist two fingers on the screen to left or right), then swipe down with one finger                      |
| TalkBack with Chrome, Firefox       | 	Swipe up then down (or swipe down then up) repeatedly to cycle through the reading controls until "Headings" is selected, then swipe down | 
| VoiceOver with Safari (macOS) 	     | Control + Option + Command + H                                                                                                             |
| Narrator with Edge                  | 	H (in Scan Mode only)                                                                                                                     |

### Navigate to headings of a certain level (e.g., to all `<h2>` headings)

JAWS, NVDA, and Narrator let you press keys 1-6 to see headings of that level.

## Landmark Regions

Screen readers announce landmarks when you enter them, like "banner region" or "main region"

### List all Landmarks

| Screen Reader & Browser             | Command                                                                               |
|-------------------------------------|---------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE | 	Insert + F3 (to open Elements List), then select Landmarks                           |
 | NVDA with Firefox, Chrome, Edge     | 	Insert + F7 (to open Elements List), then select Landmarks                           |
 | VoiceOver with Safari (iOS)         | 	Not available                                                                        |
 | TalkBack with Chrome, Firefox 	     | Not available                                                                         |
 | VoiceOver with Safari (macOS)       | 	Control + Option + U (to open rotor), then use left/right arrows to select Landmarks |
 | Narrator with Edge                  | 	Caps Lock + F5                                                                       |

### Navigate from one landmark to the next

The shift key will go backward through landmarks if held with the commands below

| Screen Reader & Browser               | Command                                                                                                                                     |
|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE 	 | JAWS 16 and above: R, JAWS 15 and below: ; (semi-colon)                                                                                     |
 | NVDA with Firefox, Chrome, Edge       | 	D                                                                                                                                          |
 | VoiceOver with Safari (iOS)           | 	Use the rotor to select landmarks (twist two fingers on the screen to left or right), then swipe down with one finger                      |
 | TalkBack with Chrome, Firefox         | 	Swipe up then down (or swipe down then up) repeatedly to cycle through the reading controls until "Landmarks" is selected, then swipe down |
 | VoiceOver with Safari (macOS)         | 	Not available                                                                                                                              |
 | Narrator with Edge                    | 	D (in Scan Mode only)                                                                                                                      |

### Navigate to the main content landmark

| Screen Reader & Browser             | Command        |
|-------------------------------------|----------------|
| JAWS with Chrome, Edge, Firefox, IE | 	Q             |
 | NVDA with Firefox, Chrome, Edge     | 	Not available |
 | VoiceOver with Safari (iOS)         | 	Not available |
 | TalkBack with Chrome, Firefox       | 	Not available |
 | VoiceOver with Safari (macOS)       | 	Not available |
 | Narrator with Edge                  | 	Caps Lock + N |