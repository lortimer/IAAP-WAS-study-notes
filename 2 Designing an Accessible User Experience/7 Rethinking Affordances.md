# Rethinking "Affordances"

## Defining Affordances

### What are affordances?

Psychologist James J. Gibson coined the term "affordances" in 1977 to refer to the range of possible actions that someone can perform with a particular object.

#### Examples:
- A door affords the possibility of being opened, of allowing passage from one side of a wall to another. Depending on the door's design and placement, a door could offer the affordance of being pushed, pulled, or sliding to the side.
- A coffee mug affords the possibility of holding things, especially, but not limited to, liquids. If it has a handle, it affords the possibility of being gripped in a place that isn't hot (if the cup holds a hot liquid) and affords the possibility of being hung on a peg by the handle.

### Affordances are not universal

An object's affordances depend on a person's capabilities. There is no single answer to what an object's affordance's are, it depends on who is using it.

#### Examples:
- The affordances of stairs depend on a person's mobility.
  - A fully mobile person: Stairs afford the possibility of moving from one level to another, either up or down.
  - A wheelchair user: Stairs do not afford wheelchair use, so they do not afford the possibility of moving from one level to another. Stairs may afford less obvious things to a wheelchair user, such as alerting them to the fact that there are multiple levels, or possibly letting them look up or down at part of the next level. But stairs do not afford wheelchair users the main purpose of their design. Stairs simply aren't designed for wheelchair users.
- The affordances of a computer screen depend on a person's vision.
  - A sighted person: A computer screen affords the possibility of perceiving visual interfaces and interacting with them using visual input methods, such as mouse or touch.
  - A person who is blind: Computer screens don't really afford anything useful to a person who is blind. They cannot perceive the visual output nor use visual methods of interacting with the visual interface.

### Binary Nature of Affordances (According to Gibson)

Considering the object and the person, affordances exist or they do not - it doesn't matter whether the person knows about them or recognizes them.

For example, a volleyball is designed to be hit with the arms or hands. Other affordances include:
  - Being kicked
  - Being sat on
  - Use as a flotation device
  - Use to break a window
  - Used as a friend on a desert island

### Donald Norman's Human-Computer Interaction (HCI) concept of affordances

In 1988, Donald Norman began to use "affordance" in a design context within HCI. He added nuance to Gibson's definition:

- An object's affordances depend on their perceivability. If a person can't perceive the affordance, it doesn't exist.
- A person's perception of affordances is influenced by their culture, background, education, etc.
- You can design an object's affordances to be obvious, or you can design it to obscure some affordances. Design quality is key to giving an object the affordances you intend it to have.

#### Examples
- A door's handle
  - A door with a plate on it is obviously for pushing, while a door with a handle is obviously for pulling.
  - A door with a handle and a sign that says "push" is hiding its own affordance.
- Web UI Input elements
  - An input with a border, a focus style, and prompt text is obviously for entering information
  - An input without a border is invisible, so the labels may just look like static text on the page. There's nothing to prompt the user to enter information
- Web UI link elements
  - A link made by an `<a>` tag is accessible by default
  - A link made with a div and some CSS and JavaScript to make it act like a link has lost all accessibility for keyboard users.

### Physical vs Cognitive Affordances

Computer Science Professor Rex Harston differentiates the two

Physical Affordance: An Emergency Exit door allows us to exit the building
Cognitive Affordance: A red, lit "Emergency Exit" sign tells us that there is an emergency exit. It allows us to know we can exit the building.

Standard visual styling of a link, blue with an underline, is a cognitive affordance. It creates an expectation in the user's mind. That link's structure as an achor tag with an href is the physical affordance.

### Designing with affordances in mind

Users have to perceive the affordances of an element to be able to use it.
- A person who is sighted will perceive affordances mainly through visual recognition.
- A person who is blind will perceive affordances mainly through sound (via a screen reader) and will discover the affordances via the semantic structure (names, roles values) of the elements in the web design.
- A person who is deafblind will perceive affordances mainly through touch (via a refreshable braille device), and, like people who are blind, will discover the affordances through the semantic structure of the web design.
- A person who is deaf will perceive affordances mainly through visual recognition, and, for the most part, will not experience disability-specific problems perceiving affordances in the interface, but will definitely experience accessibility issues with video and audio content, if there are no captions or transcripts.

