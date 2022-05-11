# Web Design Considerations, by Disability Type

This page mostly talks about stuff covered in other pages and in the CPACC course. I'm going to copy only new information here.

On mobile devices, all features require a click action. Custom swipe actions do not work with the screen reader turned on, because the screen reader itself captures them.

Pinch to zoom must not be disabled, like with `<meta name="viewport" content="user-scalable=no">`

Links, buttons, and controls **must** have a visible `:focus` state, and **should** have a visible `:hover` state

Provide large click targets

Avoid Black on White text for people with Dyslexia, but stay within the contrast range.