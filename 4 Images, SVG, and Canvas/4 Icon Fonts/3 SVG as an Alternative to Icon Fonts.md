# SVG as an Alternative to Icon Fonts

SVGs have advantages and disadvantages to icon fonts. In my opinion, images are always better because they make the
user's experience more consistent across browsers and platforms.

Here's a table of features of each. The table is only true when accessibility best practices are used. Fun note: In the class' table, they used too-small raster images of a check mark and
an X to indicate whether each option had each benefit.

| Feature                                                                                                 | Font Icons | SVG |
|---------------------------------------------------------------------------------------------------------|------------|-----|
| Icons are vector-based, rendering clearly and legibly when magnified                                    | Yes        | No  |
| Users can customize colors with accessibility utilities like Windows High Contrast Mode                 | Yes        | No  |
| Icons scale with the text when magnifying only the text                                                 | Yes        | No  |
| Icons work when images are turned off                                                                   | Yes        | No  |
| Icons can be multiple colors                                                                            | No         | Yes |
| Icons retain their original color(s) when font and background colors are changed in user preferences    | No         | Yes |
| Icons work when styles are turned off                                                                   | No         | Yes |
| Icons work when users customize the font (e.g. users with dyslexia may choose a dyslexia-friendly font) | No         | Yes |

To illustrate the argument, here are several articles about why you should use each:

- Blog article: [Bulletproof Accessible Icon Fonts](https://www.filamentgroup.com/lab/bulletproof_icon_fonts.html), by Zach Leatherman at Filament Group
- Blog article: [Seriously, Don’t Use Icon Fonts](https://cloudfour.com/thinks/seriously-dont-use-icon-fonts/), by Tyler Sticka
- Blog article: [Seriously, Use Icon Fonts](https://benfrain.com/seriously-use-icon-fonts/), by Ben Frain
- Blog article: [Ten reasons we switched from an icon font to SVG](http://ianfeather.co.uk/ten-reasons-we-switched-from-an-icon-font-to-svg/), by Ian Feather