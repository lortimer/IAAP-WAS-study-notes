# Summary Of Others

Reading through these examples and taking notes on all of them would be unreasonably time consuming, so I'm going to stop doing that and just take notes on the things I learn as I read each page.

If you ever need to implement a custom widget, just look to the [ARIA Programming Guide's Patterns page](https://www.w3.org/WAI/ARIA/apg/patterns/)

## Image Carousel (based on a tabpanel)

Only one tab is focusable at a time, so the tab key only focuses the active one. The "next" and "previous" buttons allow the user to navigate tabs. The arrow keys also allow this.

Having `role="tab` elements in a `role=tablist` element allows the screen reader to know how many tabs there are.

## Checkbox
## Checkbox (Tri-State)

A checkbox with a "mixed" state when some but not all sub-checkboxes are checked. The value `aria-checked="mixed"` is not supported by some screen readers, which will interpret it as "not checked" instead.

## Dialog (Simple Dialog)

They put text in their dialog with no `role="document"`. There is a form element, but nothing within it is described by the free text.

The tab key is constrained within the dialog - you can't tab out of it.

This dialog is for putting form elements into a dialog.

## Dialog (Simple Alert Dialog)

An Alert dialog should be brief and all text should be associated with the dialog itself using aria-labelledby and aria-describedby.

## Dialog (Message Dialog)

Confusingly, this has the same role as a Dialog, but has text instead of form elements. This time, there is a `role="document"` inside.

## Dialog (Message Alert Dialog)
## Expand/Collapse

HTML 5 offers a set of tags to do this, `<details>` and `<summary>`. Older browsers don't support this, so a button is used with `aria-expanded`.

## Expand/Collapse (based on Details/Summary)

The native HTML5 way to add an expander is to have a details outer element. Inside is a summary element and some other text elements. The summary element's contents are visible and act as a button to show and hide the other text elements.

```html
<details class="deque-expander" id="dream">
   
  <summary class="deque-expander-summary">
  	<span class="toggle-indicator"></span>
    I Have a Dream (excerpt), by Dr. Martin Luther King
  </summary>

  <div class="deque-expander-content">
    <p>And so even though we face the difficulties of today and tomorrow, 
    I still have a dream. It is a dream deeply rooted in the American dream.</p>

    <p>I have a dream that one day this nation will rise up and live out the true 
    meaning of its creed: "We hold these truths to be self-evident, that all men 
    are created equal.</p>
  </div>
</details>
```

## Link
## Navigation (Hierarchical) with Expand/Collapse

Their example doesn't even work in Firefox on Linux, it just doesn't respond.

## Predictive Text

When you start typing in a text box, options appear below it, allowing you to select one without typing the full word.

As you type, an aria-live region announces for example, "There are currently 5 options starting with A. Press down arrow for options, or press enter to select Alabama."

The example Javascript pauses for 1.2 seconds before the announcement, and the timer is reset when they type.

## Progress Bar (Bounded)
## Progress Bar (Unbounded)
## Radio and Radio Group
## Slider
## Slider (Multirange)

Mobile support (and older browser support) is unreliable with sliders of all kinds. It's best to also include text inputs to allow users an alternative way to enter values.

## Tabpanel
## Table (Responsive, Collapsible)

The table is rearranged into a list on narrow screens.

## Table (Sortable)

The sort state of the table is appended to the table's caption.

The sort state is also announced by the button that the table is currently sorted by.

Finally, the sort state is announced by aria live when it changes.

## Tooltip
## Tooltip Dialog
## Tree View