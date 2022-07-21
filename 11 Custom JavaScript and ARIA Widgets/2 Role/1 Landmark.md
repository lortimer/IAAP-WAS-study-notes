# Landmark

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