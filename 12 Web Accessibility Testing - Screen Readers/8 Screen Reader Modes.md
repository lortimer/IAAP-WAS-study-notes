# Screen Reader Modes

VoiceOver on MacOS and the mobile screen readers don't have this concept of modes. It's unique to JAWS, NVDA, and Narrator, AKA the Windows Screen Readers

## Document/Browse/Scan Mode

### Reading text

The default mode of most screen readers, this allows users to read text and navigate by sentence, word, or letter.

### Navigating by semantic elements

In JAWS and NVDA, Document mode allows you to navigate by semantic elements.

In VoiceOver on MacOS, there are no modes.

In Narrator, you have to switch to scan mode (CapsLock + Space) to navigate by semantic elements.

### Switching modes in screen readers

- NVDA: Insert + Space bar switches between document mode and focus mode
- Narrator: CapsLock + Space turns scan mode on or off.

## Focus, Application, and Forms Mode

### Focus mode

Only allows navigating between focusable elements - no text, no semantic elements. Focus mode activates automatically within application regions (not application mode??).

### Application mode

Overrides nearly all the regular keyboard shortcuts - expectation is for the dev to create their own. Should be used sparingly or not at all.

#### Regular text in application mode is not readable

Regular text is not readable, only focusable elements. To ensure it will be, you can use a couple techniques:

1. Associate the text with a focusable element with aria-labelledby or aria-describedby
2. Wrap the non-focusable text in a document region using `role=document`, which allows users to use regular shortcuts within the document region. I think this means they could still miss the text, though, because they would have to look for it with their regular shortcuts.

#### Keep the application region small

Only wrap it around pieces that absolutely must have custom keyboard event handlers.

### Forms mode

When a user enters a form field, screen readers disable all the keyboard shortcust associated with letters and numbers to allow them to type text.

When typing into a form field, screen readers will speak the letters that are typed as they are typed.

Forms mode is activated when you focus a field, not when you read through the form in document mode.

Some screen readers allow you to toggle forms mode, like NVDA with Insert + Space

#### Only focusable items—and their associated labels or descriptions—will be read when tabbing in forms

Like application mode, regular text and non-focusable elements will not be read. Any text within the form will likely be missed, including error messages about form validation. Text that is read in forms mode:

- Form labels with the `<label>` tag.
- Form labels with the aria-label attribute.
- Form labels with the aria-labelledby attribute.
- Text associated with form fields using the aria-describedby attribute (though there is a long delay in VoiceOver on Mac before that text is read).
- The text in the `<legend>` of the `<fieldset>`.
- The text inside links.
- The text in any element with tabindex="0".

## Table Mode

### Multi-directional navigation

When in a table, users can navigate in any direction from cell to cell. The shortcuts for this are Ctrl + Alt (Option) + Arrow keys on Windows and Mac.

### Table headers

When you navigate from cell to cell, the screen reader will read the table headers for that cell if there are any. It will read as many as are associated with the cell.

It usually only reads new header information. If you navigate across a row, it will read the row header and column header for the first cell, then only read the column header after that.

## JAWS PC Cursor, JAWS Cursor, & Virtual PC Cursor

### PC cursor

In JAWS, this is equivalent to the keyboard focus. Activated by the numpad "+" button.

#### JAWS cursor

Equivalent to the "mouse pointer functions". Activated by the numpad "-" button

#### Virtual PC cursor

Activated by default on web pages. A cursor that allows users to interact with text, like highlighting it, even though it's not editable. Toggled with insert + z