# Create Inclusive Designs

Inclusive design sometimes means creating one design that works for all. Most of the time, though, it means creating a single resource or process that can be used in a diversity of different ways.

## The Ability Persona Spectrum

Disabilities are not binary, they are a spectrum. Disability also includes temporary and situational limitations

- Permanent: A defining characteristic of the person's body.
- Temporary: An injury, sickness, or short-term impairment.
- Situational: A condition or context that limits a person's ability

<font size="6">Solutions that work for the extreme use cases benefit the minor use cases</font>

### Mobility/touch ability Spectrum

- Permanent: A person who cannot use their hands
- Temporary: A person with an arm injury
- Situational: A new parent holding a child in one arm

### Visual ability spectrum

- Permanent: A person who is blind
- Temporary: A person with dilated eyes from an eye exam
- Situational: A person who is driving who should not look at a computer device

### Auditory ability spectrum

- Permanent: A person who is hard of hearing
- Temporary: A person with an ear infection
- Situational: A person at a rock concert
- 
### Speech ability spectrum

- Permanent: A person who is non-verbal
- Temporary: A person sick with laryngitis
- Situational: A person in a quiet room in a library.

## An "Accessibility First" Mindset

### Learning from the "mobile first" mantra

Designing for a more extremely-constrained screen first makes designs look and feel good on all screens. It is easier to adjust a mobile first design to look natural on a wide screen than going the other direction.

### Adopting an "accessibility first" mindset

The same is true for accessibility. It is easier to build things with accessibility in mind, then make small tweaks to improve the experience for people with no disabilities than vice versa

## Collateral Benefits

Designs for people with disabilities often create unexpected benefits for others

- Curb cuts on sidewalks were designed for wheelchairs, but benefit people with strollers, carts, bikes, skateboards, etc.
- Visual and auditory announcements on trains serve people who are deaf or blind, but benefit people who can't see the screen on a crowded bus or didn't pay attention to the announcement.
- Mobile apps for train schedules benefit all kinds of people by putting information into a format that can be made accessible easily.
- Captions on television shows and movies are for deaf people, but they help you understand what's happening in a noisy environment, or if you're watching a show with accents that are hard for you to understand.
  - Captions on web content make it possible to watch a video even in a space where you have to be quiet.
- Video and audio transcripts are the only way for deafblind folks to consume video, but they make it possible for anyone to skim a video faster than by watching it.
  - They also make it possible to find videos through search engines, because the text can be indexed while the video itself cannot.
- Semantic structure on web pages forces you to organize your pages in a way that makes it easier for most people to understand.

## One Interface Fits All?

It is not possible to accommodate every need with one design, especially considering cognitive disabilities.

BUT

A single, inclusive design is almost always better than multiple

### Why not create separate designs?
- They are rarely necessary
- Users would need to know how to activate the design they need
- Separate designs continue a long history of people with disabilities using the "back door" to access things, if they can at all.
- Maintaining 2 versions is more than double the work, and feature parity would fall apart at some point.
- You can't tell which users have a disability, so you can't programmatically accommodate them.

### Should you ever create a separate design?

Users with cognitive disabilities may benefit from a separate, simplified design. An example is Wikipedia's "Simple English" pages, although users still use the same site as everyone else.

It is not possible to detect when a user is using a screen reader, which is good, because it forces us to build inclusive sites. Many users don't want it to become possible because of the potential for abuse, e.g. detecting that few users of the site use screen readers and using that to justify stopping accessibility efforts.

### What could you do if you really needed accessibility customization?
Add customization features to the site
   - A button to enlarge font size or increase contrast 
   - Manual switching between desktop and mobile views 
   - Built-in screen reader
   - Downsides:
      - Settings only apply to your site on each browser
      - It's an unexpected feature
      - Re-implementing features that exist already in a better form is a huge waste of time
      - Your features will conflict with the user's assisteve technologies
   - Upsides
      - Benefits people with minor disabilities who don't use assistive tech
      - Designer can create an accessible experience with custom components

