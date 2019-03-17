# CSS Complex Selectors
Need to stay up to date as they are constantly changing

## Direct child

```css
parentE1 > childE1 {

}
```
```html
<section> 
      <p> only selects this direct p element not the grandchildren
            <p>
                <p>
```

## Sibling
a ~ img {}

## Adjacent sibling
a - img {}

---
## Attribute selector
section [class] {}
any element that has a class in in the section

input [type=submit] {}
any input which has a type of submit

a[href*="http"] {}
an ya element that mentions http

---
## Pseudo classes

a: link
a: visited
a: hover
a: active
a: focus

input: enabled
input: disabled
input: checked
input: indeterminate


___

##  Pseudo elements

div: :before
section: :after

p: :first-letter
p: :first-line
p: :first-selection


## Targeting children
el = element your are targetting > you have to use the element your're looking for not the container
```css
el: first-child {}
el: last-child {}
el: only-child {}

el: first-of-type {}
el: last-of-type {}
el: only-of-type {}

el: nth-child(1) {}
el: nth-last-child(2n) {}

el: nth-of-type(2n) {}
el: nth-last-of-type(3) {}
```

