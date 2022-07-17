# 6 Using Forms with Screen Readers

Screen readers have different modes for reading web pages. Document mode, forms mode, application more, and virtual-cursor mode. Each has a specific purpose, and you can only be in one mode at a time. Each mode makes doing specific tasks easier.

## Forms Mode

This mode typically disables keyboard shortcuts to allow users to type into form fields. JAWS (and likely others) automatically switches from Document mode to Forms mode when you focus an input. The `<form>` tag does not trigger this, focus on a field does. Users can also manually enable forms mode.

In Forms mode, the screen reader will read each character you type.

### Only focusable items—and their associated labels or descriptions—will be read when tabbing in forms

Focus will not land on text like paragraphs, spans, headings, divs, etc. Users are liable to miss this kind of text in the middle of a form.

## Document/Browse/Scan Mode

This is usually the default mode, and it allows users to read text, navigate by word, and navigate by character to hear spelling.

They can also use this mode to navigate by semantic elements.

## Other Modes

### Focus Mode

Allows users to navigate just by focusable elements. Forms mode is a type of focus mode.

### Application Mode

Invoked by Javascript widgets with `role="application"`. The purpose is to allow devs to implement all the keyboard functionality within a widget. It disables nearly all of the screen reader's regular keyboard shortcuts. It should be used sparingly.

### Table Mode

Changes behavior of some keys like arrows to allow navigating a table. Similar to navigating a spreadsheet.