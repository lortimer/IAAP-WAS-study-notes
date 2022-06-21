# Informative Images

## Images that convey content MUST have programmatically determinable alternative text

## The alternative text for informative images MUST be meaningful (accurately conveying the purpose of the image, and the author's intent in a way that is useful to those who cannot see the image)

The goal is to provide an appropriate substitute for not being able to see the image. The alt text should represent the purpose of the image so the user understands why it is there and what it represents.

Questions to help create alt text:

- Why is this non-text content here?
- What information is it presenting?
- What purpose does it fulfill?
- If I could not use the non-text content, what words would I use to convey the same information or function?

### Informative image, general purpose
Good alt text is based on the context in which the image is used as much as the content of the image itself.

Below is good general alt text for an image:
```html
<img src="sunset.jpg" width="700" height="466" alt="The sun setting over the Pacific Ocean,
with a silhouette of a flying seagull in the foreground">
```

### Informative image, specialized purpose
In the context of a photography class, where the author wants to discuss exposure techniques and how a photo like this has over- and under-exposed portions, it's inappropriate to describe the contents of the photo. The alt text needs to describe why the author included this image, for example:

```html
<img src="sunset.jpg" width="700" height="466" 
   alt="The camera was set to properly expose the sunset in this beach scene,
   resulting in underexposure of the land and flying seagull in the foreground,
   turning them black">
```

### Informative image, logo
The following alt text does not describe the image, but serves the same purpose that the logo does for a sighted user. It is appropriate to identify it as a logo, but is not usually necessary 

```html
<img src="dequeUniversityShield.png" alt="Deque University" width="245" height="158">
```

## Alternative text SHOULD NOT include words that identify the element as a graphic or image.

Screen readers announce images by saying "image" or "graphic". Including the phrase "image of..." in the alt text is a waste of time for the user.

It's appropriate to identify that this image is a photograph or an illustration if that is important to the meaning.

## The length of the alternative text for informative images SHOULD be concise (no more than about 150 characters)

Why?
- Screen reader users can't pause and resume where they left off in the middle of the alt text
- Screen reader users can't navigate the alt text by word or character
- Some older screen readers don't read the full length

You don't have to describe every little detail of the image, just convey the meaning and purpose.

You can think of alt text like a tweet, if that helps.

### Good example
```html
<img src="herdofelephants.png" width="600"
 alt="A herd of elephants walking alongside a stream in the African Bush">
```

### Excessive example
```html
<img src="herdofelephants.png" width="600" 
    alt="In this photograph, four elephants and two calves are walking on dry land
    next to a stream of water. In the foreground, down in the bottom right corner,
    is a part of a bush. The reflection of the herd of elephants can be seen in the water.
    Behind the elephants are thickets that stretch for miles and miles.
    The thickets then give way to the mountains set in the background.">
```