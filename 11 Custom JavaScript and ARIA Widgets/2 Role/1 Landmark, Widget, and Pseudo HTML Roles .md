# Landmark, Widget, and Pseudo HTML Roles

## Landmark Roles

Landmarks are semantic sections of a page a screen reader can use to help the user navigate to the content they want. ARIA provides the following landmark roles:

- banner - page header
- complementary - for side info
- contentinfo - page footer
- form
- main
- navigation
- region - if the other roles don't apply, must include a label
- search

HTML 5 offers semantic tags that automatically have a role:

- `<header>` (equivalent to role="banner")
- `<nav>` (equivalent to role="navigation")
- `<main>` (equivalent to role="main")
- `<aside>` (equivalent to role="complementary")
- `<footer>` (equivalent to role="contentinfo")

You can use them interchangeably, or even put an ARIA role on a semantic tag.

## Widget Roles

HTML doesn't have a way to identify parts of custom widgets like trees or tab panels. ARIA provides a list of roles that are not part of HTML:

- alert
- alertdialog
- application
- dialog
- group
- log
- marquee
- menu
- menubar
- menuitem
- menuitemcheckbox
- menuitemradio
- progressbar
- separator
- slider
- spinbutton
- status
- tab
- tablist
- tabpanel
- timer
- toolbar
- tooltip
- tree
- treegrid
- treeitem

These roles allow people who can't see the UI understand what they are interacting with beyond what the HTML spec can do.

Developers cannot create their own roles. Any role not recognized by assistive tech will be ignored, or worse, cause confusion.

## Pseudo HTML Roles

You can change the role of an element, even if it has another role by default. The paragraph in `<p role="heading" aria-level="1">` is interpreted as an `h1`.

Of course, you should always use native elements when possible. The role does not bring the functionality with it, so if you create a checkbox from a div, you have to write all the Javascript to make it work as expected, and you're going to fail to do that.

The Pseudo Roles include:


- button
- checkbox
- columnheader
- combobox
- contentinfo
- form
- grid
- gridcell
- heading
- img
- link
- listbox
- listitem
- option
- radio
- radiogroup
- row
- rowgroup
- rowheader
- scrollbar
- textbox
