# Layout & Positioning 

```css
/* Positioning */

..main-header h1 {
	position: static;
	position: relative;
	position: absolute;
	position: fixed;
}
```
  
##  RESOURCES AND FURTHER READING ON FLOATS AND CLEARING FLOATS
 ([The Clearfix: Force an Element To Self-Clear its Children \| CSS-Tricks](https://css-tricks.com/snippets/css/clear-fix/)),” Chris Coyier, CSS-Tricks
[float \| MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/float)“float,” CSS: Cascading Style Sheets, MDN web docs
[clear \| MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/clear)” CSS: Cascading Style Sheets, MDN web docs
“Understanding CSS Layout And The Block Formatting Context,” Rachel Andrew, Smashing Magazine
[Getting Started With CSS Layout — Smashing Magazine](https://www.smashingmagazine.com/2018/05/guide-css-layout/)


```css
h1 {
	color: black;
}
/* targeting elements */

.myclass {
	background-color: gray;
}
/* targeting classes */

#myid {
	display: block;
}
/* targeting IDs. Must be unique per page */
``````

```css
### background

.myclass {
	background-color: transparent;
	background-image: url('myimage.png');
	background-repeat:no-repeat;
	background-position: top left;
  background: <--!SHORTHAND-->
  background-image: linear-gradient(0deg, yellowgreen, palegreen)
}

background-image: linear-gradient(0deg, yellowgreen, palegreen)
	
	border-width: 1px;
	border-style: solid;
	border-color: red;
	border: 1px solid red; /*shorthand for above*/

	box-shadow: 1px/*accross*/1px /*down*/ 1px  0px grey;

	border-radius: 10px; /*shorthand for below*/
	border-top-left-radius: 10px;
	border-top-right-radius: 10px;
	border-bottom-right-radius: 10px;
	border-bottom-left-radius: 10px;
  }

/* for targeting children */
article p {
	border-bottom: 2px solid gray;
} 
``````

## Layout

```css
	border: 1px solid white;
	width: 300px;
	margin: 30px 10px;
	padding: 20px; /*gets added onto width which can cause a problem*/
	box-sizing: border-box;
  ```
*AVOID USING HEIGHT !!!*

# /*  Centralising a web page with CSS */

```css
/*  Centralising a web page with CSS */
.wrapper { /*create a div tag with the class wrapper*/
	width: 75%; /* can be any width percentage */
	margin: 0px auto;
} 
  ```
  
  ## RESOURCES
https://learn-the-web.algonquindesign.ca/topics/css-layout-cheat-sheet/

[Getting Started With CSS Layout — Smashing Magazine](https://www.smashingmagazine.com/2018/05/guide-css-layout/)
  

