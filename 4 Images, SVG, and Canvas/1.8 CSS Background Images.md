# CSS Background Images

## Purely decorative or redundant CSS images SHOULD NOT have a text alternative in the HTML content

Alt text is not necessary for background images that serve as a background color.

## The alternative text for informative or actionable CSS images MUST be available as programmatically determinable text in the HTML content

Don't put informative or actionable images in CSS.

If you have to, you _can_ add alt text. See the following examples.

With `aria-label`. The image is applied with CSS.
```html
<a href="http://www.facebook.com/dequesystems" class="fb"
  aria-label="Deque's Facebook page"></a>
```

Using CSS Clip (I'm not going to show this example as clip is deprecated and a bad solution in my opinion)

## The alternative text (in the HTML content) for informative or actionable CSS images MUST adequately and accurately describe the purpose of the image