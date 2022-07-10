# 0 Introduction

`<canvas>` is an element that renders pixels onto the screen. Usually, Javascript is used to draw on the canvas at runtime, and it's often used for charts or games.

`<canvas>` is well supported for rendering, but its content is almost never accessible. Accessibility can be added to the `<canvas>` element itself with ARIA or Javascript. You can allso add "fallback" content within the opening or closing `<canvas>` tags.

SVG is usually better than canvas. Some other rules that will likely be mentioned in this lesson:
- `<canvas>` should not be used to display text.
- `<canvas>` must have an accessible name and description that matches content and visible text
- When used as a mouse/keyboard operable UI control, `<canvas>` must have an accessiblity role

## Canvas Example

This is an example of a canvas image. The script draws on the canvas.

```html
<canvas id="goodCanvas1" width="700" height="100" role="img"
    aria-label="A red and white circular target with an arrow  
    pointing to the center of the target"  style="margin:auto">
</canvas>
<script>
	const canvas = document.getElementById("goodCanvas1");
	const ctx = canvas.getContext("2d");
	const centerX = canvas.width / 2;
	const centerY = canvas.height / 2;
	const radius = 40;
	const radius2 = 30;
	const radius3 = 20;
	const radius4 = 10;
	ctx.fillStyle = "#eff2bc";
	ctx.fillRect(0,0,700,100);
	ctx.fillStyle = "green";
	ctx.fillRect(335,0,30,100);
	ctx.fillRect(300,36,100,30);
	ctx.beginPath();
	ctx.arc(centerX, centerY, radius, 0, 2 * Math.PI, false);
	ctx.strokeStyle = 'blue';
	ctx.lineWidth = 5;
	ctx.stroke();
	ctx.fillStyle = "#e22a2a";
	ctx.fill();
	ctx.beginPath();
	ctx.arc(centerX, centerY, radius2, 0, 2 * Math.PI, false);
	ctx.fillStyle = "white";
	ctx.fill();
	ctx.beginPath();
	ctx.arc(centerX, centerY, radius3, 0, 2 * Math.PI, false);
	ctx.fillStyle = "#e22a2a";
	ctx.fill();
	ctx.beginPath();
	ctx.arc(centerX, centerY, radius4, 0, 2 * Math.PI, false);
	ctx.fillStyle = "white";
	ctx.fill();
	ctx.strokeStyle = 'black';
	ctx.lineWidth = 3;
	ctx.beginPath();
	ctx.moveTo(250, 10);
	ctx.lineTo(centerX,centerY);
	ctx.stroke();
	ctx.beginPath();
	ctx.moveTo(345, 40);
	ctx.lineTo(centerX, centerY);
	ctx.lineTo(340,53);
	ctx.lineJoin = 'miter';
	ctx.stroke();
</script>
```