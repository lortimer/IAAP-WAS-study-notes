# 4 Single Page Applications

Single Page apps make websites faster by not loading a new page every time, but replacing content on the page. The main accessibility challenges with them are:

- Notifying users when new content is loaded (silence is bad)
- Managing keyboard focus
  - When a new page is loaded in an SPA, the content the focus was on previously disappears. This usually results in focus being lost.

## Screen reader users SHOULD be made aware when new "pages" are loaded in single-page applications.

### Move focus to the new content

- Container must have `tabindex="-1"`
- The focus MUST be temporarily moved, then sent to the correct destination.
  - This is because if the focus is already on the container where you send focus, some screen readers will not read the new content of the container.
- There MUST be a delay before sending the focus to the final destination
  - Similar to above, some screen readers are bad about losing focus on AJAX content if focus is sent too soon. Wait about 1 second.
- The focus SHOULD be sent to a heading at the beginning of the AJAX content
  - The page title isn't read on change, so this can substitute for that.

### Announce it with ARIA live.

IF it's most appropriate to keep focus on the button or link that triggered the new content, this option is ok.

- Optional: Confirm that the action is in progress. Like "Page Loading"
- Confirm the result of the action (success or failure message)
- Keep the message brief
- Choose either assertive or polite
- Optional: provide (brief) instructions related to the new content

### BONUS OPTION

In React Router, `Link` components take an optional attribute `reloadDocument` that makes your React Single-Page App behave like a Server-Rendered app. It reloads the whole document when a link with that attribute is clicked, nullifying all of the focus issues of an SPA.

```html
<Link to={"/home"} reloadDocument>Click Here</Link>
```