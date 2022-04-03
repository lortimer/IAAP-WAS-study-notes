# Key Design Concepts for Cognitive Disabilities

## Principle 1: Make it easy for users to succeed

This is design. The design should be intuitive, compelling, and successful for the user to do what they want to do. Well-defined tasks with no confusion or distractions

## Principle 2: Simplify

### Simplify the Visual Interface

Limit the number of columns, sections, widgets, and navigation links

**Single Responsibility Principle** - Each page should have one main task or feature. Anything separate from that should be minimized

### Simplify the navigation

The main nav should be as few links as possible while remaining useful.

Consider how the user intuitively looks for things (not how the business categorizes or thinks about them)

Simplify sub-menus also

### Simplify the processes and tasks

List and prioritize the core tasks of your site over others. The Flow Cytometer project is a great example. Put the target user's tasks up front, and extra features can take more clicks to get to.

### Simplify the content

The text itself and the ideas involved should be simple

Methods:
1. Summaries - provide preview summaries or conclusions for each section. Maybe a bulleted list of page highlights or a table of contents.
2. Change the content - simplify vocab, break up large chunks of text, change phrasing

## Principle 3: Provide alternative representations

Provide video, audio, images, diagrams along with text instruction.

Great example is images and video with origami instructions.

## Principle 4: Allow extra time

- Eliminate timeouts, allow extension of time limits.
- Give plenty of time to react to interactive elements
- Allow replaying of content or alternatives that allow the user to experience it at their own pace.

## Principle 5: Focus the user's attention

### Eliminate Distractions:

- Ads
- Autoplaying video or audio
- Timed interface elements like carousels
- Information that updates periodically
- Visually compelling content that isn't the main thing for the page
- Visually imbalanced designs
- Busy designs

### Present a small number of clearly-defined tasks

Emphasize the main task, get rid of the rest

### Make the experience compelling and fun

Gamification can help people with cognitive disabilities (and like, lots of people without) focus on what you want them to focus on.

Fun visual elements, audio and visual feedback, progress tracking

### Visual Design Cues

Strategies:
- Surround an important element with blank space to isolate it and draw attention
- Bold colors
- High contrast colors
- The gaze of others - literally images of people or animals looking at an important element
- Surprise - don't let it become a distraction
- Visual framing
- Arrows and other directional cues
- Pathways and leading lines
- Motion - be careful because some people can't handle motion

### Use text to draw attention

- Big bold headings
- Brevity
- Attention-grabbing words
- Punctuation
- Bold text on important words
- Summary words to highlight main ideas

### Auditory Cues

- Notification sounds
- Success sounds
- Error sounds

## Principle 6: Provide immediate feedback for both success and error scenarios

The sooner you provide feedback, the better. Success and error messages are important.

- Tell a user that form submission succeeded, failed, or is working.
- Confirmation dialog when submitting a form
- Immediate, inline error messages before submitting a form
  - Issues with screen readers: not visible unless they navigate backward
  - Many screen reader users tab through a whole form before starting to fill it out, so showing an error message when a field loses focus and is empty can be confusing.