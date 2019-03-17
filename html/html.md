 HTML
* 128 different elements
* 30-40% of elements used regularly

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<title></title>
</head>
<body>

</body>
</html>
```

* #### Elements <html>
* #### Attributes <html lang="en">
* Multiple elements an be used 
* Always close elements

### Input 
self closing element
```html
<input type="text" name="firstname"/>
```

* note on sublime - don't rename or move folders whilst working in subllime.

```html
<!DOCTYPE html>
<html>
<head>
	<title>January 7th Exercise</title>
</head>
<body>

	<header>
		<nav>Doesn't have to be at the top or side. Can be used for any section of the site that works as navigation.
		</nav>
	</header>

	<main>
		<h1>Hello World</h1>
		<article>
			<header>Header can go in other sections of  html such as article</header>
		</article>

	<aside></aside>

	<section></section>

	<div>Widely used when no other elements make sense</div>

	</main>
	<footer>
		
	</footer>
</body>
</html>
```
### Navigation
*  Some people use UL and Li elements for anchor links 



## BASIC ELEMENTS
```html
<!DOCTYPE html>
<html>
<head>
	<title>January 7th Exercise</title>
</head>
<body>

	<header>
		<h1>Hello World</h1>
		<nav>
			<a href="#">Home</a>
			<a href="">Contact</a>
		</nav>
	</header>

	<main>
		
		<article>
			<h2>My Article</h2>
			<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
			tempor incididunt ut labore et dolore magna aliqua.</p>

			<ul>
				<li>item 1</li>
				<li>item 2</li>
			</ul>

			<ol>
				<li>Chapter1</li>
				<li>Chapter2</li>
			</ol>

			<blockquote>
				<p>I am awesome</p>
				<cite>Joe B</cite>
			</blockquote>

			<details>
				<summary>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod.</summary>
			</details>

			<img src="folder/file.jpg" alt="Image of something">

			<button>
				Close
			</button>

		</article>

	<aside></aside>

	<section></section>

	<div></div>

	</main>
	<footer>
		
	</footer>
</body>
</html>
```

### Parent + children
* everything is a child of body
* use Indentatation to  keep logic of parent and children relationship

### Element flowchart
http://html5doctor.com/downloads/h5d-sectioning-flowchart.pdf

### Useful links
* *[HTML elements reference \| MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

### Other elements
```html
* Bold 
<strong>
<b>
* Italic 
<em>
* Span = use css on certain text not all  
<span>
* Sub = drops rthe text down in the line 
<sub>

<time>

*pre = renders tags and codes 
<pre></pre>

*video = must have closing tag

<video controls width="250">

    <source src="/media/examples/flower.webm"
            type="video/webm">

    <source src="/media/examples/flower.mp4"
            type="video/mp4">

    Sorry, your browser doesn't support embedded videos.
</video>

 audio 
    <audio
        controls
        src="/media/examples/t-rex-roar.mp3">
            Your browser does not support the
            <code>audio</code> element.
    </audio>


picture
<picture>
    <source srcset="/media/examples/surfer-240-200.jpg"
            media="(min-width: 800px)">
    <img src="/media/examples/painted-hand-298-332.jpg" />
</picture>

FIGURE
<<figure>
    <figcaption>Listen to the T-Rex:</figcaption>
    <audio
        controls
        src="/media/examples/t-rex-roar.mp3">
            Your browser does not support the
            <code>audio</code> element.
    </audio>
</figure>


CANVAS
<canvas></canvas>

TABLE = Used for data
<table>
	<th>Table headers</th>
	<tr>Rows
		<td>Cells</td>
	</tr>
</table>
```

## META DATA
```html
<head>
  <meta charset="utf-8">
  
  <meta http-equiv="x-ua-compatible" content="ie=edge">
  
  <title></title>
  
  <meta name="description" content="">
  
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <link rel="manifest" href="site.webmanifest">
  <!-- used for progressive web apps and where saved apps behave as native apps-->
  
  <link rel="apple-touch-icon" href="icon.png">
  <!-- Place favicon.ico in the root directory -->

  <link rel="stylesheet" href="css/normalize.css">
  
  <link rel="stylesheet" href="css/main.css">
</head>
``````
* Javascript script links should be placed just above the closing body tage to avoid blocking
