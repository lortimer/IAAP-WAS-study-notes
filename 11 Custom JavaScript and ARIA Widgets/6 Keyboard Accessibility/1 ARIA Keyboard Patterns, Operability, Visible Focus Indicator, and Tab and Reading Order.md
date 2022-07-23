# ARIA Keyboard Patterns, Operability, Visible Focus Indicator, and Tab and Reading Order

## ARIA Keyboard Patterns

ARIA includes keyboard interaction patterns more in line with desktop operating systems than traditional web schemes to give devs more flexibility and users more consistency. The [ARIA Authoring Practices Guide (APG)](https://www.w3.org/WAI/ARIA/apg/) outlines common patterns and how to implement them in a way that is consistent with user expectations. This includes keyboard interactions, roles, states, and properties.

### Tab to the widget; use arrow keys within it

In general, the ARIA pattern can be described this way: users tab to the widget, then use the arrow keys to navigate within the widget. Sometimes other keystrokes are also available, such as Home, End, Page Up, Page Down, etc., but the arrow keys are the primary navigation keystroke within ARIA widgets.

## Operability

All parts of your page must be **operable** by a keyboard, not just reachable with focus. Most assistive technology emulates a keyboard, so access with just a mouse is very disabling.

### How to test keyboard accessibility

Basically, do everything your site can do with a mouse only.


- Focus: Make sure that actionable items can receive keyboard focus, including:
  - Links
  - Form elements
  - Buttons (including "close" buttons on popups)
  - Drop-down menus
  - Tooltips and mouse-over actions
  - Modal windows and popups
  - Drag and Drop controls and objects
  - Media player controls (play, pause, volume, captions, resize, etc.)
  - Custom controls (simulated checkboxes, radio buttons, select lists, etc.)
  - Type-ahead or predictive text fields
  - Date pickers
  - Anything that users need to interact with, or that hides information from users until they request it
- Functionality: All of the controls need to perform the correct action in the expected way. For example:
  - Buttons (including submit buttons, radio buttons, and checkboxes) need to be capable of being activated with the mouse, the enter/return key, AND the spacebar.
  - Links need to be "clickable" with the mouse and the enter/return key
  - Radio buttons need to be "tabbable" as a group, but you use the arrow keys to navigate between radio buttons in the group
  - Drop-down select lists should be usable with the up and down arrow keys, or the user should be able to use alt + down arrow to expand the list, then use the arrow keys within the list, and use the enter/return key to select the option.
  - ARIA widgets should follow the design patterns outlined in the ARIA authoring practices opens in a new window


## Visible Focus Indicator

Sighted users need to be able to see where keyboard focus is at all times.

Browsers have a default focus indicator that is considered acceptable, but can be made more visible.

### Don't turn off the focus outline

Just don't. And feel free to go off on any designer or dev who suggests you do.

### You can enhance the visual focus indicator

```css
a:focus {
    background-color: #fdf6e7;
    outline: 1px solid #8cc63f;
}
```

Why not make it fit your design's color scheme? Why not make it much more obvious than a 1 pixel dashed line?

You probably need multiple indicators to fit with your elements, like a light-colored indicator and a dark one. Also different ones for links and buttons.

### You can also enhance the hover and active states

Helps users with low vision.

```css
a:focus, a:hover, a:active {
    background-color: #fdf6e7;
    outline: 1px solid #8cc63f;
}
```

## Tab/Reading Order

### The linear tab/reading order is determined by the DOM

The order things are in the DOM is the order they will be read. Remember, the DOM is interpreted source code, not source code itself. Generally the order will be the same in both.

### Make the tab/reading order match the visual order

Don't style things to be in weird positions that don't match the reading and tab order.

Exceptions like modal windows are ok.