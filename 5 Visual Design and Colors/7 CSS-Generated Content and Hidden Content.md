# CSS-Generated Content and Hidden Content

CSS-Generated content is read by some, but not all screen readers. It is generally not treated as a "fully integrated part of the DOM" by browsers, so it is not always available to assistive technologies

Generating content with CSS and visually hiding elements should be done with caution.

## CSS-Generated Content

### CSS-generated content SHOULD be avoided

Supported by:
- NVDA + Firefox
- NVDA + Chrome
- VoiceOver on OS X + Safari
- VoiceOver on iOS + Safari

Not Supported by:
- JAWS + Internet Explorer
- Narrator + Edge

#### Example of CSS Generated Content

It can be appropriate to use generated content for printing purposes, because print media is unlikely to be relevant to users of screen readers.

```css
span::before {
   content: "This is the generated prefix ";
}
span::after {
   content: " and this is the generated suffix";
}
```

### A text alternative for informative CSS-generated content MUST be provided, AND the CSS-generated text SHOULD be set to `aria-hidden="true`"

Because only some screen readers support it, hiding it from all screen readers and creating an HTML alternative is the only way to create a uniform experience.

### Decorative or redundant CSS-generated content SHOULD be set to aria-hidden="true"

## Visually Hidden Content

### Visually hidden and inactive content MUST be hidden from screen reader users until that content is made visible and active for sighted users

Hidden content, like inactive dialogs and collapsed menus, should be hidden from all users, not just sighted users. The goal is to create an equivalent experience, so screen reader users should not have to deal with "seeing" a dialog that is hidden and they can't interact with.

`display:none` and `visibility:hidden` hide an element from all users.

### When additional content is triggered on pointer hover or on keyboard focus, that additional content MUST be dismissible, hoverable, and persistent

Examples of this are tooltips, context menus, navigation bar menus, except for ones managed by the browser, like built-in tooltips.

Users must be able to dismiss the new content without moving the mouse or keyboard focus when the new content obscures page content. For example, if a menu obscures part of a page, a keyboard user should be able to dismiss it with the Escape key, leaving their focus on the element it was already on.

Users must be able to hover their mouse pointer over the pop-up content. Some users magnify the screen, and need to be able to pan to the new content with their mouse, and others have content read to them as they mouse over it.

Content should not disappear until keyboard or mouse hover leaves it. Be generous with the hitboxes on this, nothing is more annoying that having to carefully guide your mouse from the content to the pop-up so it doesn't disappear. The disappearance shouldn't be time-based, either, so people have adequate time to understand it.

#### Bad Example: Content is not dismissable

A menu that is not dismissable unless the user clicks away, is not dismissable at all.