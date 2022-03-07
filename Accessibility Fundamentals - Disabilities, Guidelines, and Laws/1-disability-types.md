# Types of Disabilities and Design Considerations

## Blindness
Blind people often use screen readers to read aloud the content of the screen

- All content must be presented in text or with a text equivalent like `alt="description of image"` for images.
- Information must not be conveyed by visual attributes alone
- All functionality must be available using only the keyboard (Note: be sure to test with the screen reader turned on, because there are subtle differences in keyboard behaviors when the screen reader is on).
- The content must use markup with good structure and semantics (headings, landmarks, tables, lists, etc.).
- All custom controls (e.g., expand/collapse buttons, media player volume control, dialogs, etc.) must have the correct name/label, role (either with HTML or with ARIA), and value, and must change value when appropriate (e.g. aria-expanded="false" changes to aria-expanded="true" after activating the button).
- Users must receive immediate feedback after all actions, via their screen reader. Silence after activating a feature is always bad!
- Videos require audio descriptions (additional narration of visual content) if the video's original audio track (dialog, sounds, narration) does not explain everything that a person who is blind would need to know to understand the video.
- On mobile devices, all features require a click action. Custom swipe actions on web pages will not work with the screen reader turned on.

## Low Vision
Low vision is different for everyone and is caused by many things. People with low vision often use screen readers or software to zoom in on the screen.

- The pinch-to-zoom feature must not be disabled (avoid `<meta name="viewport" content="user-scalable=no">`).
- All text must pass contrast guidelines against the background
- Links, buttons, and controls must have a visible :focus state and should have a visible :hover state.
- The user interface should provide a clear visual distinction between content (e.g., text) and controls (e.g., buttons, links, etc.)

## Color Blindness
Color blindness is an inability to distinguish certain colors from one another, even if they look different to people without color blindness. The most common kind of color blindness makes red and green difficult to distinguish. Other types make blue and yellow or red and black look the same. Very rarely, someone may not see color at all.

**Don't use only color to communicate information**

Rather than trying to design for specific types of color-blindness, designers should communicate all information by more than just color.

## Deafness
Most of the web is accessible to people with auditory disabilities because it's mostly a visual medium. Video is an exception

- Video should have captions as well as a written transcript. Transcript should have descriptions of music and other sounds. 
- Sign-language interpretations of video can help. 
- Transcripts help make the video accessible to people who use screen readers as well.

## Deafblindness
Some people are both deaf and blind. The only way they can interact with the web is through a braille display, which has small pins that can be raised or lowered to display some text. With a screen reader, the braille display can allow someone to read a web page one piece of text at a time.

Transcripts of video are the only way for someone with deafblindness to perceive a video.

## Motor Disabilities
A wide range of disabilities that affect someone's ability to move some or all of their limbs. People without use of their arms and legs can use the internet when websites are accessible!

- All functionality must be available using only the keyboard.
- Links, buttons, and controls must have a visible :focus state and should have a visible :hover state.
- With session time-outs, warn users before the time expires (e.g. an accessible dialog or alert), and give them the option to extend the session. Ensure the warning itself allows for slow responses. A recommended minimum response time is 2 minutes.
- Provide large click targets (links, buttons, controls) for users who have movements that are difficult to control.

## Speech Disabilities
Some people cannot form words correctly. Other people just pronounce things in various ways because of their accent.

- Don't depend on speech alone for input!

## Cognitive Disabilities
A huge range of disabilities caused by congenital conditions, developmental conditions, or brain injury.

### Limited Comprehension
- Simplify the interface and keep it consistent across pages
  - Limit the number of choices on the screen
- Use simple language
- Use images and text to convey information
- Provide help features
- Keep audio and video short

### Memory Loss
- Retain information across screens within a path
- Provide help features

### Distractability
- Reduce or eliminate distractions like popups, auto-playing videos, or things unrelated to the content.

### Limited Problem-Solving
- Captchas can be difficult to solve, leading people to give up
- Provide help through error messages - why did something fail?

## Dyslexia
- Avoid black text on white background (but maintain high enough contrast)
- Supplement text with images, video, and audio

# Seizure Disorders
- Avoid flashing - anything faster than 3 times per second