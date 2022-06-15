# Lists

## Semantic Markup for Lists

### Lists MUST be constructed using the appropriate semantic markup

There are 3 types of list:
- Unordered lists `<ul>` with list items `<li>` that render with bullets. Should be used when the items can be put in any order.
- Ordered lists `<ol>` with list items `<li>` that render with numbers or letters. Should be used when the items have an intrinsic order.
- Definition lists (HTML5 calls them Description Lists) `<dl>` have paired **terms** `<dt>` and **definitions** `<dd>`. Description lists pair a term with its definition, or a name with a value.

Screen readers announce lists and how many items they contain, so making a fake list with a table or other elements prevents users from understanding the list.

#### Good Example: Unordered List
```html
<p> These are a few of my favorite things</p>
<ul>
     <li>Raindrops on roses</li>
     <li>Whiskers on kittens</li>
     <li>Bright copper kettles</li>
 </ul>
```

VoiceOver would read this list as
> These are a few of my favorite things.
> 
> List 3 items.
> 
> Bullet, Raindrops on roses.
> 
> Bullet, Whiskers on kittens.
> 
> Bullet, Bright copper kettles.

JAWS reads it about the same, but ends with "list end".

#### Good Example: Description List

```html
<p>Cryptids of Cornwall:</p>

<dl>
    <dt>Beast of Bodmin</dt>
    <dd>A large feline inhabiting Bodmin Moor.</dd>

    <dt>Morgawr</dt>
    <dd>A sea serpent.</dd>

    <dt>Owlman</dt>
    <dd>A giant owl-like creature.</dd>
</dl>
```
Voiceover reads this in the following way

> Cryptids of Cornwall.
>
> Description List 3 items.
> 
> You are currently on a description list. To move between items in this list press control option right arrow or control option left arrow.

When you navigate items, it reads the first one like this: "_Beast of Bodman, 1 of 8. You are currently on a text element_". Then you navigate to the next, and it says: "_A large feline inhabiting Bodmin Moor., 2 of 8. You are currently on a text element_". You can navigate early to cut off the voice and hear:

> Beast of Bodman...A large feline inhabiting Bodmin Moor.
> 
> Morgawr...A sea serpent

and so on.