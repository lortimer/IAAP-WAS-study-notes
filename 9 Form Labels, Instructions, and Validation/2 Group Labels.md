# Group Labels

Group labels are required for things like a group of radio buttons. Each has its own label, but the group of them
together needs a label also.

## Semantic Group Labels

### Group labels MUST be programmatically associated with the group if the individual labels for each element in the group are insufficient on their own

#### Good Example: `fieldset` and `legend

The legend serves as the label for the group. Some screen readers read the legend once, others read it for each input,
so keep it short if possible. VoiceOver reads each individual label _followed by_ the legend, which sucks, but there's
nothing to be done about it. VoiceOver users know it does that.

**Nested fieldsets are safe to use**

```html

<form>
    <fieldset>
        <legend>Contact Information</legend>
        <p><label for="name6044">Name: </label> <input type="text" id="name6044"></p>
        <p><label for="phone6044">Phone: </label> <input type="text" id="phone6044"></p>
        <p><label for="email6044">Email: </label> <input type="text" id="email6044"></p>
    </fieldset>
</form>
```

#### Good Example: ARIA

A container with role `group` and `aria-labelledby` achieves a similar result. This doesn't work right with VoiceOver,
and has never been fully supported, so `fieldset` is preferred

```html

<p id="grouplabel9961">Contact Information</p>
<div role="group" aria-labelledby="grouplabel9961">
    <p><label for="name">Name: </label> <input type="text" id="name"></p>
    <p><label for="phone">Phone: </label> <input type="text" id="phone"></p>
    <p><label for="email">Email: </label> <input type="text" id="email"></p>
</div>
```

### Group labels MUST be programmatically determinable

## Meaningful Group Labels

### Group labels MUST be meaningful

### Group labels MUST NOT rely solely on references to sensory characteristics

Not only color, images, etc. Make sure a text alternative exists

## Proximity of Group Labels

### Group labels SHOULD be visually adjacent to the grouped elements

### Group labels SHOULD be adjacent in the DOM to the grouped elements

## Visibility of Group Labels

### Group labels MUST be visible