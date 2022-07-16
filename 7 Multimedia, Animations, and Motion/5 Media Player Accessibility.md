# Media Player Accessibility

## Keyboard Accessibility

### All functionality of a media player MUST be available to keyboard users

As with any complex, custom UI element.

#### All controls must be tab-focusable
#### The tab order must be logical
#### All controls must have visual focus indicators
#### The functionality must work with the keyboard
#### The focus must be managed logically during interactions
#### Provide keyboard instructions for any unusual controls

## Screen Reader Accessibility

### All controls of a media player MUST present the correct names, roles, and values to screen reader users

This includes:

#### Name
"Play", "Pause", "Volume", etc.

#### Role
Most often `button` or `slider`

#### Value
What is the current setting? What has it changed to?



## Captions, Transcripts, and Audio Descriptions

### Media players SHOULD allow users to access captions, transcripts, and audio descriptions

#### Option 1: Provide accessibility features in the media player itself

Like AblePlayer does. Actually, why not just use AblePlayer?

Some widgets use a single symbol like the Closed Captions symbol to encompass the whole accessibility menu, which can be confusing.

#### Option 2: Provide the accessibility features in alternate ways

This is basically always more work for a less-flexible outcome!

## Customizability

### Media players SHOULD allow visual customization of captions

### Media players SHOULD remember user preferences.

### Media players SHOULD allow full screen video