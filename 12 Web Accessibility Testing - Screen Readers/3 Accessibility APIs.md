# 3 Accessibility APIs

Every major OS has an accessibility API, which allows screen readers to access information about the objects and events available to the user.

## Windows

The current Accessibility API on Windows is called "UI Automation" and was introduced in Windows Vista, though it has gone through other iterations. The older one, Microsoft Active Accessibility or MSAA is still used by some legacy software.

### Inspecting the Accessibility API

#### Inspect.exe

You have to install the Windows 10 SDK, then run this. It should be set to UI Automation mode, not MSAA mode. This app is in Program Files > Windows Kits > 10 > bin > [your platform]

This software looks like dev tools but in its own window for the OS, although it has information about the accessibilit of the selected thing.

#### The Edge F12 Accessibility Tree

A similar UI, but in the developer tools panel.

## MacOS

The Accessibility API was introduced in version 10.2 and rewritten for version 10.10 to be more similar to the iOS accessibility API. It is backward compatible with the old one.

### Inspecting the accessibility API

It is accessible through XCode. When the app is open, it is under the XCode Menu > Open Developer Tool > Accessibility Inspector. To use the inspector, gover the mouse over objects and view the panel to see the accessibility tree.

## Browsers

### Browser accessibility architecture

Browsers have their own accessibility tree, similar to the DOM but with more specialized purpose. It skips DOM nodes that aren't meaningful Each accessibility tree node contains information about:

#### Name
The text label given to the element. Sometimes the name is the text within the element itself (e.g., link text or heading text). Other times the name must be assigned with either an HTML method (e.g., `<label>` elements for form fields or `<caption>` elements for HTML tables), or via an ARIA attribute (i.e., aria-label="This is the name" or aria-labelledby="someID").

#### Description
Extra information about an element (e.g., as defined by aria-describedby="someID" or by the title attribute, depending on the context).

#### Role
The semantic meaning of the element, which can come from native HTML elements (e.g., headings, tables, lists, etc.) or ARIA roles (e.g., role="tablist", role="tab", role="tabpanel", etc.).

#### Property
Characteristics of an element (e.g., haspopup="true").

#### Relationship
Each relationship generally follows one of these patterns:

- Parent-child hierarchies, which are often defined by the natural hierarchy of the DOM. For example, an HTML list item (<li>) must belong to a list (<ul> or <ol>), and an ARIA tab must belong to a tablist.
- The explicit linking of an element to the element it belongs to or controls (e.g., as defined by aria-owns="someID" or aria-controls="someID").

#### State
The current condition of an element (e.g., `aria-expanded="false"` or `aria-selected="true"`).

### Internet Explorer

Used MSAA, which didn't provide all the information that screen readers needed. They had to rely on aditional methods to make IE accessible.

### Firefox

Works well with NVDA and JAWS on Windows, Talkback on Android. Does not work well with VoiceOver on MacOS. The implementation of accessibility features is incomplete.

### Safari

Works very well with VoiceOver.

### Chrome

Good support, works with NVDA and JAWS, which targets it specifically. MacOS? The internet doesn't know.

### Edge

Chromium, so basically the same as Chrome.