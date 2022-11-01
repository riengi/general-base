# CSS Grid Layout
* [W3 Schools](https://www.w3schools.com/css/css_grid.asp)

## Elements
* columns
* rows
* column gaps
* row gaps
* column lines (1...x)
* row lines (1..y)
* grid template (rows and columns) 

## Block level grid container (taking width)
```css
.grid-container {
    display: grid
}
```

## Inline-grid container 
```css
.grid-container {
    display: inline-grid;
}
```

## Adding column and row gaps
```css
.grid-container {
    display: grid;
    column-gap: 50px;
    row-gap: 50px;
}
```

## Placing grid item between columnt line 1 and 3 and row lines 2 and 3
```css
.item {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start:2;
    grid-row-end:3;
}

## Grid template where all 3 columns are auto width
```css
.grid-container {
    display: grid;
    grid-template-column: auto auto auto;
}```

## Grid template with 3 columns given dimensions
```css
.grid-container {
    display: grid;
    grid-template-column: 80px auto 40px;
}```

## Grid template with row template
```css
.grid-container {
    display: grid;
    grid-template-row: 80px 200px;
}
```

## Justify container content (justify-content)
* space-evenly : even space across the grid
* space-around : even spece for each element
* space-betweeen elements : maximum space between elements
* center : elements to the center
* start
* end

```css
.grid-container {
    display: grid;
    justify-content: spce-evenly;
}
```

## Placing items
Items starts on column 1 and ends before column 5
```css
.item1 {
    grid-column: 1 / 5;
}
```
Items starts on column 1 ands spans 3 columns
```css
.item1 {
    grid-column: 1 / span 3;
}
```
Item starting on row 2 and ending before row 5
```css
.item1 {
    grid-row: 1 / 5;
}
```
Item starting on row 2 and taking 2 rows
```css
.item {
    grid-row: 2 / span 2;    
}
```

## Placing based on grid-area
Combining row and and column location definition
Rectangle like definition (row, column) .. (row, column)
```css
.item1 {
    grid area: 1 / 2 / 5 / 6

}
```
## Named grid item taking 3 columns in layout
```css
.item {
    grid-area: myArea;
}
.grid-container {
    grid-template-areas: 'myArea myArea myArea'
}
```

## Named grid item gaking 2 columns in 5 column layout
```css
.grid-container {
    grid-template-areas: 'myarea myArea . . .';
}
```

## Named grid item taking three column (of 5) and two rows
```css
.grid-ontainer {
    grid-template-areas: 'myArea myArea myArea . . ' 'myArea myArea myArea'
}
```

## Named items page example
```css
.item-header { grid-area: header; }
.item-menu { grid-area: menu; }
.item-main { grid-area: main; }
.item-right { grid-area: right; }
.item-footer { grid-area: footer; }

.grid-container {
    grid-template-areas {
        'header header  header  header  header'
        'menu   main    main    main    right'
        'menu   footer  footer  footer  footer'
    }
}
```
## Ordering/positioning the Items 
We can reshufle the items (r_start, c_start, r_end_ c_end)
```css
.item1 { grid-area: 1 / 3 / 2 / 4}
.item2 { grid-area: 1 / 1 / 2 /2 }
```

### Rearanging order for certain screen size
```css
@media only scree n(max-width: 500) {
    .item1 { grid-area: 1 / span 3 / 2 / 4;}
    .item2 { grid-area: 2 / 3 / 3 4; }
}