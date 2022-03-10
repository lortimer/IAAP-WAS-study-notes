# Avoid Exclusive Design Patterns

Accessibility problems are the result of biased design decisions. The idea that a user has trouble with a design because of their disability is backwards. The design creates a disabling situation for some people. A better design is not disabling.

Whether someone can engage fully with a designed environment is based on the design, not the person. Humans have just systematically excluded disabilities from their designs as a general practice.

## Examine Assumptions

Exclusion is the opposite of accessibility. Limiting factors in the environment make it inaccessible to some people based on their abilities.

Not examining our biases leads us to design only for our own assumptions about the world

## Designs that Cause Exclusion

"What in the design of the environment excluded this person?"

Understand the characteristics of the person that are incompatible with the environment, but from the perspective of figuring out a better design for the environment. The person is not at fault.

Buildings used to mostly have stairs leading to the entrance. The shift in perspective that the design is flawed and not the people is what lead to laws requiring accessible buildings.

## Learning from Accessibility Design Failures

### Failure to design

Most common accessibility design failure. Many people aren't aware of the need.

What is the goal? Web accessibility doesn't happen by accident.

Planning makes the goal possible.

A well-planned site makes it easy for anyone to get around and find the things they need.

A site without accessibility can feel chaotic, like a kitchen where all the tools and utensils are scattered throughout and disorganized. It takes a lot of frustrating trial and error to find what you need, and simple tasks take much more effort.

### Ineffective Designs

Everyone needs to know some accessibility, but you need some experts working on the hard stuff, too.

On the web, it's easy to ignore guidelines or take shortcuts. Some Common issues:
- No semantic markup
- Custom widgets (like alerts or components that change while the user is looking at them) without ARIA markup to announce changes
- Custom components without proper keyboard focus management.
- Poor color contrast
- Form validation with visual or even color-based cues only - what went wrong?

### Incomplete Designs

The team knows enough to do a bad job.

Bad built environment examples:
- A door that blocks the wheelchair ramp
- A ramp that leads to stairs
- Curb cuts in two sidewalks with an island that has no curb cuts between them
- Disability parking space with no curb cuts

Bad Web examples
- An accessible dialog with an inaccessible button to open it
- `aria-hidden="true"` on accessible elements - they can be tabbed to, but the screen reader will say nothing
- Bad, custom tab order

## Bad Retrofitting

Making a bad design accessible

Inelegant retrofits are often ok if they are temporary. Nothing is as temporary as you plan for it to be.

Bad built environment examples:
- Long, zig-zagging ramp
- Putting accessibility features behind inaccessible ones.

## Inconvenient or Stigmatizing Designs

Accessible entrance in the back, alley, kitchen, near the dumpsters, etc.
- Separate experiences based on ability
- Calls attention to someone's disability
- Evokes racial segregation

Web Examples:
- "Accessible version" of a site
- Accessible by phone but not website
- Accessible PDFs available upon request
- Clunky, unintuitive fallback pattern for widget designed without accessibility in mind
- Text description of an inaccessible widget - you don't get the experience of using it.

## "Accessibility Rot" Over Time

Built examples:
- Barriers like flower pots on wheelchair ramps
- Dumpster in a disability parking spot
- Permanent fixtures in above scenarios

On the web, your site can grow inaccessible over time as HTML and ES change. Also, future developers need to maintain and add to accessibility features, so you better set good patterns and make it hard to add to the site without accessibility features.

It's not a one-time project!