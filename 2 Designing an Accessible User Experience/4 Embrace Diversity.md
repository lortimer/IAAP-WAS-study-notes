# Embrace Diversity

People with disabilities are diverse just like people without. Disabilities themselves are diverse. The categories to
consider:

- Blind
- Low vision
- Colorblind
- Deaf
- Deafblind
- Dexterity/motor disabilities
- Speech disabilities
- Cognitive disabilities
- Reading disabilities
- Seizure disorders

Some people have multiple disabilities

## Examining the Edge Cases

Designing for the middle of the bell curve gets you about 68% of users.

Picking users at the edges and making sure their conflicting needs are met can cover nearly 100% of users.

It's like the software Menlo built for a flow cytometer. The target persona was a grad student, so the features that
were easiest to get to and use were the ones that grad students need. The more complicated features were still there for
the advanced users (scientists and professors), but they didn't get in the way of the easy, more common use cases. The
advanced users can confidently navigate and find the features they need, the students need not to be overwhelmed.

### Challenge: Video games for people who are blind

Imagine you are given the task of designing online video games for people who are completely blind. They can't see the
screen at all, so you don't have to make it look good. In fact, you don't need a graphic user interface at all.

Input: Typically, people who are blind use keyboards to input information into the computer. With video games, you have
some room for additional creativity. Are there ways of making other input devices — like a mouse, a joystick, a game
controller, a motion detection device, a voice recognition device, etc. — work for people who are blind?

Output: They're going to be using a screen reader to hear the output of the game. They'll also be able to hear the audio
of the game itself. They won't be able to see the screen, so everything will have to be available through audio, or, if
you get more creative, perhaps through tactile feedback.

- How would you approach this design challenge?
  - Depends on the genre.
    - A text-based adventure or graphic adventure game like Monkey Island would be pretty easy to adapt for blind people with audio cues and voice acting.
    - A time-based game would be harder. The whole idea of the game would likely have to revolve around audio cues.
- What kinds of assumptions will you need to discard to make this project a success?
    - Video games need graphics
    - The user can see and react in ~200ms to the game (time it takes for a visual signal to make it to the brain and
      elicit a response.)
- Which kinds of interactions would be easy to make work for people who are blind? Which types would be most difficult?
    - Harder
        - Real-time reaction-based genres like platforming, fighting, FPS, RTS, physics
    - Easier
        - Turn-based genres like Tactics, RPGs, board games
- Are there some types of interactions that would be impossible?
    - I don't think so, but you'd have to be very creative to preserve some kinds of mechanics. For example, a
      platformer could use sound to indicate proximity to the edge of a platform or enemy, the positions of things in
      the world, and when you had discovered something.
- If you design a video game primarily for people who are blind, would it also work for people who can see?
  - Yes, as long as the people playing it had the same abilities as those for whom it was designed. A design for a blind person would likely depend a lot on sound, so someone who can see but not hear would likely not be able to play it, unless the design included visual indicators for all the audio cues as well.

### Challenge: Video games for people with limited mobility
Now let's consider a different group of people: people who cannot use their hands well enough to use standard video game interfaces. Perhaps they cannot use their hands at all, or perhaps they have tremors in their hands, limiting their precision, or perhaps they lack grip strength and the ability to move quickly. There are many variations in human mobility.

Input: There are a wide variety of input methods for people with motor disabilities. Here are a few:

- Eye-gaze tracking devices that allow users to point and select with their eyes
- Single-switch devices that allow users to push a single button to interact with an on-screen keyboard and on-screen menus of context-sensitive options
- Sip and puff devices that allow people to use their breath to control an on-screen keyboard and on-screen menus of context-sensitive options
- Voice recognition software that allows users to select items on the screen (by their label or ID) and interact with them via context-sensitive menus and commands
- A mouth stick (a stick with rubber tips on both ends) to type and use a trackball mouse

Output: Assuming the person does not have multiple disabilities, the output would be the visual and audio output that people with sight and hearing would expect. There are no special output considerations for this use case.


- How much overlap is there between the needs of a person who is blind and a person with limited mobility when playing video games?
  - Time-based games can be difficult for both groups.
  - A design for people with limited mobility needs to focus on inputs where a design for blind people needs to focus on output 
- If you completely solve the challenge for one group, how relevant are those solutions to the other group?
  - Some would be and some wouldn't be.
- If you solve the challenges only for these two use cases and completely ignore users without disabilities, how much overlap is there? Do these two use cases cover all the needs, or will you need a third use case for people without disabilities?
  - I think they cover all the needs in that the game would be playable by people without disabilities.

## User Research with People with Disabilities