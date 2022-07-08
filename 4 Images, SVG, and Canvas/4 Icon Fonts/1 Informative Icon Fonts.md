# Informative Icon Fonts

## Informative icon fonts without accompanying visible text SHOULD be assigned role="img"

```html
<p>Have a great day 
    <span class="fa fa-smile-o" role="img" aria-label="Smiley face"></span></p>
```

## Informative icon fonts without accompanying visible text MUST have a text alternative

Although it is possible to add alternative text via hidden text (using position:absolute; clip:rect(0 0 0 0), without assigning role="img" (Who would ever think to do this?), this usually isn't the best method, for three main reasons:

- The icon font is not recognized as an image.
- On mobile devices, the visible icon font is not available to screen reader users when using the "explore by touch" method.
- VoiceOver on OS X focuses separately on the icon font item and then on the hidden text, even when the icon font is set to aria-hidden="true".

## Actionable icon fonts without accompanying visible text MUST have a text alternative

Fucking icon buttons. Designers love 'em.

### Good Example

```html
<p id="text-editor">
   <button><span role="img" class="fa fa-bold" aria-label="Bold"></span></button>
</p>
```

### Good Example: alt text on the button itself

If it's not important for the screen reader user to be able to identify the icon font as an image, it can be acceptable to place the alternative text (`aria-label` or `aria-labelledby`) for the icon font on the link rather than on the icon font itself. The icon font will not appear in the list of images, but the link will have accessible text. To ensure screen readers don't mispronounce the font icon, `aria-hidden` is added to it.

The title attribute is optional. It adds a popup tooltip that may help sighted users clarify what the icon means. Some screen readers will read both the `aria-label` text and the `title` text, so this technique should be used with caution.

In my opinion this is more trouble than it's worth in most cases.

```html
<p>Enter your username 
   <button id="usernameExample" aria-label="More info about user name" 
      title="More info about user name">
      <span class="fa fa-question-circle" aria-hidden="true">         
      </span>
   </button>
</p>
```

## The alternative text for informative icon fonts MUST be meaningful

### Bad Example

Using "?" as the alt text for an icon of a question mark in a circle.

```html
<p>Enter your username 
   <button>
      <span class="fa fa-question-circle" aria-label="?"></span>
      <!-- screen readers will literally say 
      "question mark" or "question" -->   
   </button>
</p>
```