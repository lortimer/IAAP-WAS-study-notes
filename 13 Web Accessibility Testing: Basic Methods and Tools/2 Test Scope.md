# Test Scope

What is the scope of the test you're going to conduct?

- Are a few pages going to be evaluated, or an entire web application?
- Will the evaluation stick to informational content or will it also cover transactional processes?
- Which pages are going to be evaluated?
- How can the best pages be selected to get the most out of the evaluation process?

You don't necessarily have to test all the pages on a site when evaluating for accessibility, but the pages you do test should be representative of the pages you don't, and your specific recommendations should apply to tested and untested pages.

## Entire Pages
### Test Priority

The course recommends focusing on the following to choose which pages to test, in this order:

1. Anything that occurs across the entire site, such as templates that are reused on multiple pages.
2. Anything used to navigate, such as navigational menus.
3. Anything used to accept payment or to commit the user (or organization) to a legal contract, such as Forms.
4. Anything used during primary interaction with the site.
5. Anything typically found to cause accessibility problems: Images, Forms, Tables, Frames, Interface Elements relying on client-side scripting, and Media.
6. Anything typically used by persons with disabilities, such as site maps.
7. Anything necessary for contacting the organization, such as contact forms and staff directories.
8. Anything that gets a lot of traffic, such as the Home page or any of the pages that receive the top 80% of traffic.

You should adjust the priority based on how frequently a feature is used and how impactful that feature is - i.e. does it occur in high- or low-traffic areas?

### Selecting Pages for Evalutation

Choose pages that have the most diversified and representative content, semantics, and structure. Evaluate pages that contain the widest variety of features.

You should also look at pages built by different people or teams, because each dev and team has different strengths. You want to make sure you see accessibility issues across the organization.

### Selecting Templates for Evalutation

If there are page templates used, you should evaluate some pages from each one.

## Page Content, Components, and Widgets

### Selecting specific content for evaluation

Images are the most common problem area for accessibility because the alt text may be missing, or more likely, inadequate. Especially for sites where image use is significant, you should test units that allow you to evaluate several images for adequate alt text.

Tables are another common problem area, especially when they are complex.

Forms are very important because they allow the user to submit information, and they often lead to a formal relationship like a purchase, payment, contract, or the storage of private information. Tests should include forms and ensure robustness and error checking.

Frames are not too common these days, but have lots of accessibility challenges. 

Multimedia is a high-impact area and is often inaccessible. Focus tests on ensuring that audio and video meet the requirements for text-based alternatives and time-based concerns like speed, rewinding, etc.

### Selecting Custom Widgets and Client-Side Scripting for Evaluation

You should also make sure to check any reusable components because the impact of your evaluation is more widespread. This includes one of each of things like dialogs, accordion menus, table sorting, data loading, progress indicators, etc.