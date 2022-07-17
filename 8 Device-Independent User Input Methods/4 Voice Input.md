# Voice Input

Some users cannot use mouse and keyboard because of motor disabilities or stress injuries. Most operating systems have some voice recognition built in, but there is 3rd-party software that has more features. Most of the principles of making a web page accessible also apply to voice-recognition input, including:

- Keyboard compatibility for all functionality
- Visible instructions for non-traditional keyboard interactions
- Visible keyboard focus for interactive elements
- Clear indication of what content is actionable and what is not
- Programmatically associated labels and form fields
- Unique and meaningful link text
- Accurate alt text for actionable images
- Accurate semantics for actionable controls
- Adequate click target size

## Dragon Naturally Speaking

This is commercial software to execute commands by voice. I will include information about it here to give examples of how a user might use their voice to input commands.

###  Examples of usage

#### Listing all of a type of element and choosing one to activate

If you wanted to see all links on the page and choose one to click, you would first say "Click link". This would assign a number to every link on the page and display the number next to each one. You could then say "Choose 7", which would click link number 7.

#### Clicking a specific element

If you want to click a link you can already see that says "Visit the Dequeue home page here", you can say "Click 'visit the Dequeue home page here'". The same applies to buttons and labeled fields.

#### Navigating the page

"Press tab", "scroll up", "go to bottom", "reload", and "go back" are among the commands you can use to navigate.

#### Navigating with Mouse Grid

Let's say a particularly bad developer made a "clickable" div with custom Javascript, but did not assign it a role or tabindex. The voice commands may not work to click this button. The solution is mouse grid.

You can say "mouse grid", which creates a grid overlay on the screen, dividing the screen into 9 numbered sections. If the button is in section five, you just say "five". Section 5 will then be divided into 9 numbered sections. You repeat this process until the grid encompasses what you want. You can then say "click" to click the "button".

You can also use this to place the pointer for other reasons, like click and drag.



### Support for ARIA

As of 2014, Dragon supported some but not all ARIA roles. This kind of exception is why it's important to build pages with native elements when possible.