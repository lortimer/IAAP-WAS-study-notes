# Allowing Customizability

## Visible text SHOULD be standard text in the markup (not images or graphic versions of text), to allow user customization of text color and contrast

Essentially, using text in markup rather than images of text means users can customize the colors.

## Visible UI components SHOULD use native controls and features (not images or graphic versions of controls) where available, to allow user customization of interface color and contrast

Don't make a PNG of a button with text on it and use `<img role="button" />`. Use native controls with real text in them.