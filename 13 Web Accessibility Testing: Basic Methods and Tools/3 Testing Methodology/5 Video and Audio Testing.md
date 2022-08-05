# Video and Audio Testing

The biggest thing here is to ensure there is a text alternative to the video and/or audio. See the Multimedia, Animations, and Motion course notes for information about when captions, transcripts, audio descriptions, or sign language are required and at which compiance level.

## Testing Methodology for Video Only

For presentations that contain only video (visual) content:

1. First, check to see if an audio description track or text description of visual content is necessary. If important visual information is not conveyed anywhere, audio description or text description is needed.
2. If an audio or text description is provided, check that it accurately describes important visual content in the video (You may need to watch the entire video to ensure audio description or text description is accurate).
3. If a text description is provided, make sure it is near the video it describes and can be easily found by all users.

## Testing Methodology for Video and Audio

Captions must be provided. Transcripts and audio descriptions may or may not be required.

### Captions

1. Look to see if captions are available, either through open captions (captions that are always on, cannot be turned off) or closed captions (look for a closed captions button or some way to turn on captions).
2. If captions are available, check for the following:
    1. Captions are in sync with the spoken audio content.
    2. Captions are accurate. If the content is scripted, captions should be verbatim (including "um's" and stuttering). If content is unscripted, captions should be as close to verbatim as possible (but "um's" and stuttering may be omitted).
    3. If multiple speakers are present onscreen, then speakers are identified in the captions.
    4. Any important sound effects (e.g., music that sets the mood) are captured and described in the captions.
3. Make sure automatic captions aren't used because they are often inaccurate.

### Transcripts

1. Check to see that a transcript is available.
2. If a transcript is available, it should be near the multimedia presentation and easy to find (either on the page itself or provided through a link).
3. Check the transcript for accuracy. The transcript should include the following:
    1. All spoken words
    2. Descriptions of important non-verbal sounds (noises, music) that contribute to the experience
    3. Identification of speakers
    4. Descriptions of important visual content — transcripts are intended for people who cannot hear or see the content

### Audio Description

If an audio description track is necessary, check that it accurately describes important visual content in the video (You may need to watch the entire video to ensure the track is accurate).



## Testing Methodology for Audio Only

1. Check to see that a transcript is available.
2. If a transcript is available, it should be near the audio presentation and easy to find (either on the page itself or provided through a link).
3. Check the transcript for accuracy. The transcript should include the following:
    1. All spoken words
    2. Descriptions of important non-verbal sounds (noises, music) that contribute to the experience
    3. Identification of speakers



## Testing Methodology for Media Players

Media players have to be fully keyboard accessible and screen reader accessible.

### Testing for Keyboard Accessibility

To evaluate media players for accessibility, check that the following are true:

1. All controls can be accessed using the Tab key.
2. The tab order for the controls is logical. It should reflect the visual order of the controls.
3. All controls have visual focus indicators. When keyboard focus is set on a control, there should be a visual border around the control so users know where the focus is.
4. All controls can be activated using the keyboard. The Enter key and Space bar should activate button controls; and the volume slider and progress slider should be controlled using the down arrow, up arrow, right arrow, and left arrow keys.
5. Focus is managed throughout all user interactions. For instance, if a control activates a modal dialog (e.g., caption preferences), focus is moved to the dialog. When the dialog is closed, focus moves back to the control that activated the modal dialog.
6. If there are any custom controls in the media player, instructions for how to operate them by keyboard are provided.

### Testing for Screen Reader Accessibility

You should test with at least two, but that probably means on each platform.

1. The name of each control is conveyed to the screen reader. The screen reader should render names of controls like "Play," "Pause," and "Volume" so that users know what the control is.
2. The role of each control is conveyed to the screen reader. Slightly different from the name, the role identifies the element the control uses, such as a button or a slider. Together with the name, the screen reader should render something like "Play button" or "Volume slider".
3. The value of certain controls is conveyed to the screen reader. In the case of using a slider for volume, the control should identify the value to users so that users understand changes. For example, if a user decreases the volume from 100% to 80%, the screen reader should announce the values "100%, 90%, 80%".

