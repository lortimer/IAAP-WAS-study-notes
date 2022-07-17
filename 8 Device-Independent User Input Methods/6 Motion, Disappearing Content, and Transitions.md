# Motion, Disappearing Content, and Transitions

Interactive elements that move are difficult to use. Animations and transitions can cause accessibility problems, especially if they are fast.

## Motion Actuation

### Functionality that can be operated by device or user motion MUST also be operable by user interface components and MUST allow the ability to disable motion actuation

This is the only reason I was able to play Wii games given how bad the motion controls were. There have to be standard ways of activating functions controlled by motion. Other examples include shaking your phone to activate the flashlight or camera.

Users also have to be able to disable the motion controls so they don't accidentally trigger them.

#### Exceptions

- The motion is used to operate functionality through an accessibility supported interface (that is, supported by assistive technology as well as by features in browsers and other user agents)
- The motion is essential for the function (for example, a pedometer or GPS-based applications)


## Moving or Disappearing Content

### Content SHOULD NOT move in a way that makes interactive elements difficult to activate

The Bad example is a link within a marquee element. If someone I worked with did that, I would either fire them or quit on the spot.

A more realistic bad example is a warning/confirmation dialog that appears for 1 second, then automatically chooses the more destructive option.

## Transitions that Affect Interaction

### Transitions SHOULD NOT interfere with reading or interaction, unless the interference is brief

5 seconds is the limit between brief and not. Slow transitions have a host of problems for people with cognitive disabilities, motion sensitivities, or use screen readers.

[A good example provided by the course](https://dequeuniversity.com/assets/html/module-input-methods/transitions/goodtransitionexample.html)

[A bad example provided by the course](https://dequeuniversity.com/assets/html/module-input-methods/transitions/badtransitionexample.html)

### Transition effects SHOULD be kept to a minimum (to avoid nausea, dizziness, annoyance, etc.)

### Parallax effects SHOULD be kept to a minimum, in terms of the total number of parallax effects, the amount of parallax within each individual effect, and the size of the area affected