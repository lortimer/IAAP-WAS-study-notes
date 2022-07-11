# 2 Contrast

**There are nearly 3 times more individuals with low vision than with total blindness**. 

**About 1 in 12 people has some sort of color deficiency** - 8% of men and 0.4% of women in the USA.

## Text Against the Background

### Small text (under 18 point regular font or 14 point bold font) MUST have a contrast ratio of at least 4.5 to 1 with the background

This means most text is small text. This rule serves people with low vision and color deficiencies.

This rule applies to backgrounds with patterns, gradients, images, and videos. USE A SOLID COLOR BACKGROUND.

### Small text (under 18 point regular font or 14 point bold font) SHOULD have a contrast ratio of at least 7 to 1 with the background

Friendship over with 4.5:1. Now 7:1 is my new best friend. This ratio can mean users with low vision of 20/80 or better don't need to enhance contrast.

4.5:1 isn't great for mobile devices, 7:1 is the goal.

### Large text and images of large text (at or over 18 point or 14 point bold) MUST have a contrast ratio of at least 3 to 1 with the background

1 point equals 1.333 (repeating, of course) CSS pixels. 18pt font is the same as 24 px font. 

## Non-Text Contrast

### Any visual boundary that indicates an active user component's hit area (the region where a pointer can activate the control) MUST have sufficient contrast of at least 3 to 1 with the adjacent background

Buttons, form elements like inputs, links, etc.

This only applies if the visual indicator of a boundary is the only way to identify the component, it MUST have sufficient contrast. I can't think of an example of one that this wouldn't apply to. Maybe this means a bordered component with a fill the same color as the background?

Default colors set by the user agent are out of your control and therefore exempt from this rule.

### The visual state of an active user interface component MUST have sufficient contrast of at least 3 to 1 with the adjacent background

An active component is one that is not disabled, meaning one that is available for user interaction.

Visual States include focus, selected, unselected, and others.

Default colors set by the user agent are out of your control and therefore exempt from this rule.

### Parts of graphics (required to understand the content) MUST have a contrast ratio of at least 3 to 1 against adjacent color(s)

Informational icons, lines in graphs, slices in pie charts, etc.

Exceptions are instances where changing the color changes the meaning, including:
- The colors of flags
- Photography
- Heatmaps

But you should choose colors and backgrounds for those that don't disable people unnecessarily.

## Focus Indicator

### The contrast of all visual focus indicators against the background MUST be at least 3 to 1

In some browsers, the default visual indicator is not easy to see, especially against certain background colors. Enhancing the visual indicator alleviates this problem.

Designers take note, it can be done in many different ways, not just a dotted line. highlighting, color changing, even shape or size changing.

## Boundaries Between UI Components

### Whenever visual boundaries are used to distinguish controls, the contrast of UI control boundaries compared to adjacent areas MUST be at least 3 to 1 to distinguish the UI control from the adjacent areas

Buttons and links have to be distinguished from non-interactive text. The bad example given here is in a music player mobile app. The music playhead and the title of the song are buttons, but look the same as non-button text like the time remaining in the song.

Another very common example of this is a text input that is editable but looks like non-editable text because there is no border on the text input. Worse yet is when such inputs start empty and are completely invisible against the background.

## Testing for Sufficient Color Contrast

You have to use analysis tools for this, you can't tell just by looking.

Now's a great time for an advertisement for Dequeue's Axe accessibility checker!

[WebAIM](https://webaim.org/resources/contrastchecker/)
[Axe](http://www.deque.com/products/axe/?__hstc=213731083.79b4221141dd46346a82c2b9be8acf67.1652736854609.1652965527556.1653051713247.8&__hssc=213731083.6.1657544321655&__hsfp=3145755274)
[Dequeue's Color Checker](https://dequeuniversity.com/color-contrast)
[Adobe](https://helpx.adobe.com/ca/creative-cloud/adobe-color-accessibility-tools.html)

## Windows High Contrast Mode

In Windows 10, you can turn this on in the system settings. Search for "high contrast" in the taskbar search field. If you press Windows+U, it brings up accessibility settings, including high contrast.

Windows offers 4 themes. High Contrast #1, High Contrast #2, High Contrast Black, and High Contrast White. The High Contrast Black theme features a black background, white text, yellow links, bright green disabled text, and highlights selected text in turquoise and black text. High Contrast White uses a white background, black text, blue hyperlinks, maroon disabled text, and highlights selected text using dark blue background and white text. High Contrast #1 and #2 themes are variations of the High Contrast Black theme.

You can customize all of them, but all 4 are sufficient for testing. You should test with one black and one white theme.

Non-Edge Browsers have to be configured to use the system's high contrast setting.
- Firefox: Open Menu > Options > Content > Colors... (Under Fonts & Colors) > Select Use systems colors in the dialog box
- Will detect that you are using a high contrast theme on the computer and will prompt you to install a high contrast extension in the browser; It does not use the high contrast theme from the computer

### Web content SHOULD retain all essential visual information in Windows High Contrast Mode
- Don't use background images that convey information because they may be hidden
- Use real text, not images of text
- Don't rely on color alone

### The design MUST NOT override Windows High Contrast Mode

The Microsoft-specific -ms-high-contrast media feature and -ms-high-contrast-adjust CSS property can override user's high contrast themes in Internet Explorer. DON'T USE THEM.