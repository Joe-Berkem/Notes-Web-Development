# CSS Grid

* Usually 12 columns
* put classes on your sectioning elements
* span the number of columns you specify
* Used for laying out the page
* It's DOM dependents
* It's pretty new - 2017

To use: 

```css
display: grid
```
** Add display grid but ONLY THE DIRECT CHILDREN ARE CONTROLLED

specify umber of rows and columns on the container! 
```css

.wrapper {
  display: grid
  grid-template-rows: 20% 20% 20% 20% 20%;  /* = 5 equal rows */
  grid-template-columns: repeat(3, 1fr); /* = 3 equal columns using fraction. auto auto auto would have the same affect*/

}
```
* fr only available for grid at the moment.
* minmax() function = 

### Grid Gap 

```css
grid-gap: 1rem;
```
Good for equal space as there is only one value so it has to be equally spaced. You can still use margin and padding if items are not equally spaced.

### Grid template areas
```css
grid-template-areas: 
  "header header header"
  "main main aside"
  "main main"
  ".footer."
  ```
  
  Once the areas have been named in the container you can start adding the elements and aligning the declared names
  
  ```css 
  header {
     grid-area: header
     }
  ```
  
  ## Numbers in grids
  * Grid numbers start at 1
  *  Each row/column is automatically given a number. 

```css
main {
    grid-row: 2/3; /*starts at 2 ends at 3*/
    grid-column 1/2; /*starts at 1 ends at 2*/
}
```
shorthand = 
  ```css
main {
    grid-area: 2/1/3/2;
    /*starts at row start, column start, row end, column end*/
}
```


### Aligning Children
* Add justify items or align items on the parent.
* Justify self or align self will go on the children

```css 
.wrapper {
    justify-items: start;
    align-items: stretch;
}

.wrapper-child {
jusify-self: center;
align-self: start;
}
```

@ supports declaration can help with browsers that don't support grid.