# Introduction

This module presents the elements needed to establish an accessibility testing program within an organization, the steps involved in the accessibility evaluation process, and the types of web accessibility testing techniques and methodologies. This module also presents a sample methodology that can be used to maximize efficiency in testing for accessibility.

## Accountability for Testing

### Testing Should Be an Integral Part of the Development Life Cycle

I know this as a developer. Testing is best done alongside the creation of the code.

#### Planning and Design

When planning a project, accessibility should be considered as a part of the user requirements. Designs should be tested with potential end users, including end users with disabilities. Especially if the product being designed is non-standard in some way.

Designers can consider the accessible flow of any web pages they are designing by adding tab stops to the design, designing how to present text-only versions of multimedia, and describing the user's experience with custom widgets using a screen reader, keyboard only, and mouse only.

#### The Build/Creation Phase

Writing automated tests as you write the code, especially when they focus on accessibility, helps a lot. React Testing Library is a great example of a test library that strongly encourages focusing on accessibility with the tests, and through it produces valuable unit tests that don't focus on implementation.

Tools like your IDE can point out accessibility problems, and Axe DevTools can point out issues that appear in the DOM.

Developers should be able to test their content with a keyboard and using screen readers.

#### The "Testing" Phase

I think the course means running large, manual build tests before deployments or a major release. QA should know about accessibility, and the team's accessibility experts should be involved. Hiring people with disabilities on your team means they can provide a user's perspective during this process.

Test results should be reported in a specific way that allows developers with no accessibility expertise to fix them.