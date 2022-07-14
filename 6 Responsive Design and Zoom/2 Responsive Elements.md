# Responsive Elements

**NO HORIZONTAL SCROLL BARS ALLOWED**

## Responsive Forms

### Forms SHOULD reflow to fill most of the width of the viewport, without causing any horizontal viewport overflow

When changing viewport size, forms should adjust so that:

- Form fields do not overflow the viewport
- Form fields and their labels are not separated by extensive whitespace that makes it difficult for people who use
  screen magnifiers to associate labels and fields

Labels should almost always be above the input on narrow screens.

## Responsive Images

### Images SHOULD reflow to fill most of the width of the viewport, without causing any horizontal viewport overflow

#### Good Example: Image Max Width 100%

Prevents the image from exceeding the bounds of the viewport

```css
@media (max-width: 320px) {
    main img {
        max-width: 100%;
        height: auto;
    }
}
```

#### Good Example: Image chosen from srcset

You specify a set of comma separated source files, each optionally followed by a width descriptor (positive integer followed by `w`) and/or a pixel density descriptor (a positive float followed by `x`). These values interact with values specified in the `sizes` attribute, if any, to choose a source file based on the viewport size.

```html
<img 
    src="medium.png" 
    srcset="small.png 400w, medium.png 600w, large.png 900w"
    alt="Wheelchair racers in the Paralympics speed down the track" >
```

#### Good Example: Assign Image Size Using the `<picture>` Element

The `<picture>` element is a robust feature and will serve only the desired image to the device.

```html
<picture> 		
    <source 		
        media="(min-width: 40em)" 		
        srcset="
            large.png   900w, 		        
            medium.png  600w, 		        
            small.png   400w" /> 	
    <source 		
        srcset="
            small.png" /> 	
    <img src="medium.png" 
        alt="Wheelchair racers in the Paralympics speed down the track" /> 
</picture>
```



## Responsive Objects and Plugins

### Objects/plugins SHOULD reflow to fill most of the width of the viewport, without causing any horizontal viewport overflow

`max-width: 100%` on the object's container is a surefire way to limit it to the viewport's width. 



## Responsive Tables

### Tables SHOULD reflow to fill most of the width of the viewport, without causing any horizontal viewport overflow

Smaller tables may fit just by resizing the columns

Large tables can be reflowed to be displayed in a single column.

#### Good Example: Table in Single Column

Take this table for instance:

|                          | City of Birth | Current City | Favorite City |
|--------------------------|---------------|--------------|---------------|
| Ernesto Trivoli          | 	Naples       | 	Rome        | 	Naples       |
| Margarita de Rosas       | 	Mexico City  | 	Los Angeles | 	New York     |
| Kristin Mumfordson       | 	Berlin       | 	Stockholm   | 	Cambridge    |
| Samson Abrahamson 	      | Tripoli       | 	London      | 	Jerusalem    |
| Sahara Blackstone-Carver | 	Atlanta      | 	Boise       | 	Nairobi      |

Below is a screenshot of this table reflowed into a single column. For each row, a header displays a person's name. Below that, each column is displayed inline with text centered. It looks a little like JSON data.

<img src="https://dequeuniversity.com/assets/images/module-visual-design/table-responsive.png" alt="Screenshot of the table above reflowed into a single column">

