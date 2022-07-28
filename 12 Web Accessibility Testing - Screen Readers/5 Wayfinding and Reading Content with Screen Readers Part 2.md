# Wayfinding and Reading Content with Screen Readers Part 2

## Lists

Screen Readers announce what kind of list, how many items, and if there are sublists.

### Show All Lists

ONLY JAWS has this function (at the time the course was published?), with a shortcut of Insert + Control + L

### Navigate from one list to the next

| Screen Reader & Browser             | Command                                                                                                                                                                                                                                                                                                          |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE | 	L                                                                                                                                                                                                                                                                                                               |
 | NVDA with Firefox, Chrome, Edge     | 	L                                                                                                                                                                                                                                                                                                               |
 | VoiceOver with Safari (iOS)         | 	Use the rotor to select lists (twist two fingers on the screen to left or right), then swipe down with one finger. Note: You may need to change your VoiceOver settings to allow lists to be available with this gesture. To change the settings, go to Settings > General > Accessibility > VoiceOver > Rotor. |
 | TalkBack with Chrome, Firefox       | 	Not available                                                                                                                                                                                                                                                                                                   |
 | VoiceOver with Safari (macOS) 	     | Control + Alt + Command + X                                                                                                                                                                                                                                                                                      |
 | Narrator with Edge                  | 	Not available                                                                                                                                                                                                                                                                                                   |

### Navigate from one list item to the next

Only JAWS and NVDA can do this, with the "I" key.

## Navigating Sequentially

When you first open a page, the screen reader will read the whole page if not interrupted. Most people don't let this happen on a regular basis. However, when they find a landmark, heading, or other element of interest, you can have it read from that point on.

### Read continuously from this point

| Screen Reader & Browser             | Command                                                                                                                                                                   |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE | 	Insert + Down Arrow                                                                                                                                                      |
 | NVDA with Firefox, Chrome, Edge     | 	Insert + Down Arrow or Numpad Plus                                                                                                                                       |
 | VoiceOver with Safari (iOS) 	       | Two finger swipe down                                                                                                                                                     |
 | TalkBack with Chrome, Firefox       | 	Open the TalkBack menu by swiping down then right or up then right, then repeatedly swipe right until you reach "Read from next item," then select it by double-tapping. |
 | VoiceOver with Safari (macOS)       | 	Control + Option + A                                                                                                                                                     |
 | Narrator with Edge                  | 	Caps Lock + Down Arrow or Caps Lock + Control + R                                                                                                                        |

### Read next or previous line

| Screen Reader & Browser               | Command                                                                                                                                                          |
|---------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE 	 | Next: Down Arrow Previous: Up Arrow                                                                                                                              |
| NVDA with Firefox, Chrome, Edge 	     | Next: Down Arrow or Numpad 9 Previous: Up Arrow or Numpad 7                                                                                                      |
| VoiceOver with Safari (iOS)           | 	Next: Rotor, swipe down Previous: Rotor, swipe up                                                                                                               |
| TalkBack with Chrome, Firefox         | 	Swipe up then down (or swipe down then up) repeatedly to cycle through the reading controls until "Lines" is selected. Then Next: Swipe down Previous: Swipe up |
| VoiceOver with Safari (macOS)         | 	Next: Control + Option + Right Arrow (Read next item) Previous: Control + Option + Left Arrow (Read previous item)                                              |
| Narrator with Edge                    | 	Next: Control + Down Arrow Previous: Control + Up Arrow                                                                                                         |

### Read next or previous sentence

| Screen Reader & Browser             | Command                                    |
|-------------------------------------|--------------------------------------------|
| JAWS with Chrome, Edge, Firefox, IE | 	Next: Alt + Down Arrow Previous: Alt + Up | Arrow
 | NVDA with Firefox, Chrome, Edge     | 	Next: Alt + Down Arrow Previous: Alt +    | Up Arrow
 | VoiceOver with Safari (iOS) 	       | Not available                              |
 | TalkBack with Chrome, Firefox       | 	Not available                             |
 | VoiceOver with Safari (macOS)       | 	Control + Option + S (Read sentence)      |
 | Narrator with Edge                  | 	Not available                             |

## Previous and Next Items

### JAWS and NVDA

Up and Down arrows navigate by segment. 

These screen readers define segments in terms of its own buffer, rather than the actual markup in the code, so JAWS may pause in the middle of a sentence or at another seemingly random location.

### VoiceOver on iOS

Swipe right to go to the next element, or swipe left to go to the previous element. VoiceOver on iOS defines elements logically like VoiceOver on Mac, so it will pause at the end of a sentence, link, span, etc.

### TalkBack on Android

Swipe right to go to the next element, or swipe left to go to the previous element.

### VoiceOver on macOS

Use Control + Option + right arrow to navigate to the next element, and Control + Option + left arrow to go to the previous element. VoiceOver defines elements in more logical groupings than JAWS or NVDA, so VoiceOver will pause at the end of a sentence, link, span, etc.

### Narrator

Type the down arrow on the keyboard to go to the next segment (or up arrow to go backward to the previous segment).




## Navigating Through Focusable Items with the Tab Key

Use tab to skip between natively-focusable elements and things with `tabindex="0"`. The screen reader will read the text or label for each thing. Make sure the text makes sense out of context. For instance, a link that says "next", "more" or "click here" don't make sense without the surrounding text.

### The Tab key on mobile devices

You can connect an external keyboard, but otherwise there is not direct equivalent. You can select to navigate by links or form controls, but not all focusable elements. To navigate other focusable elements, you have to just swipe right or left until you find what you're looking for.