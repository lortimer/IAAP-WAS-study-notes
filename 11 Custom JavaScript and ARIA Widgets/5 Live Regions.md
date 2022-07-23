# Live Regions

`aria-live` lets you make announcements to the user without their input. You create an empty container marked as a live region and insert text into when you need to make the announcement. The screen reader is listening for those announcements.

## Assertive versus polite

### Assertive

`aria-live="assertive"` will interrupt the screen reader if it is reading other text. The previous text will stop and not be continued after the announcement.

If multiple assertive announcements occur at the same time or close together, they may interrupt each other, because assertive announcements are not usually queued.

### Polite

`aria-live="polite"` enqueues the announcement so it is read after the screen reader is done reading the current text.

## ARIA live announcements SHOULD be brief

They cannot be recovered if they are stopped, so minimize this risk with short announcements. You also can't reread them unless you find them on the page.

## The ARIA live region MUST be empty to begin with

## The ARIA live region MUST be recognized by the accessibility API before text can be injected into it

Wait at least 2 seconds after page load, or after adding an empty live region to the page.

## Modifier attributes for aria-live regions

### `aria-atomic`

- `aria-atomic="false"`: The default. It means that when a change is made to a live region, the change can be read on its own, excluding the other stuff already in the live region.
- `aria-atomic="true"`: When changes occur in the live region, the whole region is read.

### `aria-relevant`

- aria-relevant="all"
  - All changes are relevant. Use sparingly - when overused it can be very detrimental to the usability.
- aria-relevant="additions"
  - Insertion of nodes to the live region are relevant. For example, nodes that are removed from the top of a log are merely removed for purposes of creating room for other entries, and the removal of them does not have meaning.
- aria-relevant="removals":
  - Removal of nodes to the live region are relevant (i.e., a screen reader will speak the removal).
- aria-relevant="text"
  - Changes to the textual content (including text equivalents, such as alt text) in the live region are relevant.

`all` and `removals` should be used sparingly. Removals aren't usually relevant, but an example case would be "buddies" leaving a chat room.

### aria-busy

This suppresses announcements while a region is updating. All the updates will be announced when the value is changed from true to false.

## Different types of aria-live regions

### `role="alert"`

An assertive live region that can announce impportant information. Some screen readers announce "alert" when this is used.

### `role="status"`

A polite, atomic region. Some screen readers say "status" before an announcement. Other's treat this just like `aria-live="polite"`

### `role="timer"`

A region containing a timer counting up or down. By default, this has `aria-live="off"` because timers usually update quickly.

### role="marquee"

Designates a region as an area of scrolling text, like a stock or news ticker. By default, this has `aria-live="off"`.

### `role="log"`

Keep a record of sequential events, like a chat conversation. The order of new content matters - it should come at the end of the region. Defaults to polite and non-atomic