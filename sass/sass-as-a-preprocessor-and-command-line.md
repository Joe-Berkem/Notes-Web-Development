## Sass as a preprocessor + command line

CSS and html = declarative languages ⇒ html you’re declaring data, css is just attaching things to the html. There’s no functionality in these languages (cf functional languages like JS and ruby) → so preprocessors were developed → sass and less 

Sass is kind of the go-to now, though less is still used.

NB. sass gives more functionality but it has to be processed for your browser to need it, so you need a css file → a browser cannot read a sass file.

You’ll include the sass files in your <head> and then we’ll make sure this compiles into css.

## .scss/.sass
.sass = first version of sass and depends heavily on whitespace, so we don’t use this (ie. relies on indentation to get rid of braces, semi-colons and other punctuation symbols, leading to a leaner and shorter syntax → looser)
.scss = newer version, more similar to css and what we’ll be using (for saving files out from sublime)

### Why use sass?
To make CSS easier to manage and easier to read:

We have variables in sass - can give things a name eg. the colour codes above, to make them easier to refer to and easier to read. Means you can just change everything in one place instead of having to go through the whole code:


NB. don’t put colour names in the variables (group names).

### Sass Features

CSS values as variables:
Anything you can put as a value can be cast into a variable.

Format: $ + variable name + : + value + ;

They have to be declared first to be able to use them.

NB. Sass does have a linter - so if you miss out semicolons and colons etc (syntax errors), sass will pick it up and won’t compile. If you use a wrong value, it will still compile, but the css just won’t run.

### Nesting:

Makes code neater. Instead of listing everything out like below...


You can nest them all under say a ‘nav’, like below:

NB. be careful you don’t nest too deeply (no more than 3 or 4 levels)as anything more means we’re probably getting too specific in the way we write our css.

You can also nest media queries. So instead of putting one big media query at the bottom of the page, you can put it inside the actual element. Eg. if there’s a mq for nav, you could just put it in the nav nest element - so essentially you’ll be writing different media queries for different elements - keeps everything related together in one place.

Using ‘&’: https://css-tricks.com/the-sass-ampersand/

### Extends: 

Lots of elements with green background. Rather than write a green class in html, write it in your sass.

Format: % + class name  then to use  @extend + %classname

While variable will only take a value, extend will take a whole block of properties and values. Can use this method with classes too.

### Functions:

Lots of extra functions in sass (look up in the documentation as won’t cover everything now: 
https://sass-lang.com/guide; http://sass-lang.com/documentation/Sass/Script/Functions.html ).
Mixins:

A bit like extends. Will pass in the code, but get to use a parameter.

Format: @mixin + name (whatever you want) + ($howmuchradiusetcyouwant) + { + any properties you want changing + }

Not an actual variable, just the notation. Have to set the parameters. This block of code will only do something when you set it up.

 http://sass-lang.com/documentation/file.SASS_REFERENCE.html#mixins 

http://krasimirtsonev.com/blog/article/SASS-mixins-extends-and-placeholders-differences-use-cases 

### Imports:
http://sass-lang.com/documentation/file.SASS_REFERENCE.html#import

This has always been a css spec, just wasn’t supported very well in the past.

Lets you import other css or sass files - so you can write lots of sass files, import them into one file and that file can be the file we create the css from. This means you can change the other style files as much as you want.

Just type the path of the file that you want relative to the file that you’re in.

A browser cannot read a sass file - so how do we make them into css files?


## Command Line & SASS

The above shows i’m working with ruby, so I’d need to use colons in the below task rather than just a space:

sass --watch sassfile.scss:cssfile.css
Not
sass --watch sassfile.scss cssfile.css)

The above changes our main sass file into a css file, which the browser can then read. We’ll be importing all our sass files into the main sass file, so everything will be converted into this css file.

**Changing a css file (grid.css) into a sass file** :
Change file working on yday to grid.scss (so from style.css to grid.scss) - want to give each style sheet a relevant name followed by .scss eg. colours.scss; layout.scss:

**Open grid.css in sublime**
Now we’re going to make a sass file that will import all these individual scss files into one place → style.scss:
Create a new style.scss file in sublime and save in the same folder as grid.scss
Import grid.scss (@import ‘grid.scss’;)
Go into Terminal, navigate to where all sass files are saved:

Enter this (specific for my version and files): sass --watch style.scss:style.css 
Press return and it will show that sass is watching style.scss for changes:

This watches the main sass file (style.scss) for changes and turns it into a main css file (style.css) which the browser can then read (as it can’t read scss files)
Do not change the style.css file as this will override the above and lose your work - this file will compile automatically
We will be creating individual css files every time we want to do a bit of styling (eg for buttons, fonts, grid etc) then importing them into the style.scss file by using @import, so eventually the style.scss file will just look like a list of @import functions:


The terminal will detect any updates (while it’s open) eg. making a colours.scss file for all the colour values for the site:



If anything isn’t working, check the terminal.

To check that the file you're trying to open actually exists, you can change directories in terminal using cd. To change to ~/Desktop/sass/css: cd ~/Desktop/sass/css. To see what files are in the directory: ls.
If you want information about either of those commands, use the man page: man cd or man ls, for example.
Google for "basic unix command line commands" or similar; that will give you numerous examples of moving around, viewing files, etc in the command line.
On Mac OS X, you can also use open to open a finder window: open . will open the current directory in finder. (open ~/Desktop/sass/css will open the ~/Desktop/sass/css).
https://stackoverflow.com/questions/9547730/how-to-navigate-to-to-different-directories-in-the-terminal-mac
https://learntocodewith.me/command-line/unix-command-cheat-sheet/

**Install sass syntax package in sublime**

NB. can also remove packages this way and see which packages you have installed.

In box that appears type ‘sass’ > select ‘sass’ (or ‘syntax highlighting for sass’) if that’s not there), press enter:


Then open up your scss file (so grid.scss) and go to View > Syntax > Sass > scss 

Exercise: start using sass on project site

NB.
Don’t switch terminal off/close it down, otherwise will have to do all the above again to watch the scss file
When making separate css files and importing remember the order you import them is important. Eg. if you make a file for colours, import it first/high up in the list so that you can refer to the colours in later files.

Sass functions
Variables begin with dollar signs, and are set like CSS properties. You can then refer to them in properties:
$width: 5em; #main { width: $width; // width is set as 5em }
On the other hand, Mixins allow you to define styles that can be re-used throughout the stylesheet
@mixin large-text { // defining mixing font: { family: Arial; size: 20px; weight: bold; } color: #ff0000; } .page-title { // applying mixin @include large-text; padding: 4px; margin-top: 10px; }
The above code is compiled to:
.page-title { font-family: Arial; font-size: 20px; font-weight: bold; color: #ff0000; padding: 4px; margin-top: 10px; }
https://stackoverflow.com/questions/43841041/what-is-the-difference-between-a-variable-and-a-mixin-in-sass


Sass style guide (CSS tricks)
https://css-tricks.com/sass-style-guide/

How to structure a sass project
http://thesassway.com/beginner/how-to-structure-a-sass-project





Some CSS that hasn’t been mentioned:
Presentation: https://gitpitch.com/pitchme/print/github/develop-me/fellowship-wk2-adv-html-css/master/white/PITCHME.pdf?p=day08%2F02coolCSS 

Cursor:


There a quite a few different ones: https://developer.mozilla.org/en-US/docs/Web/CSS/cursor

List style:

You can put an image in, eg if someone wants a custom bullet. But easier to use background image.

Transforms:
Relatively new. Can translate it - moving things along x,y,z (zoom) axis
Can scale, rotate, skew etc just like a graphics package

Tend to string them up together - putting a space between each type ⇒ 1 transform

Transitions & animations:


Further reading: https://css-tricks.com/almanac/properties/t/transition/

Transitions:-
Property (color) how long you want it to transition (0.2s) how you want it to transition (ease).

Animations:-
Declare your animation with @ anywhere in the CSS file. Specify the different points (from 0-100%) that you want to animate). To use it, put it on the element you want to animate:


Blend modes:
Various types of blend modes.
Eg. Getting images to fade into their own backgrounds/a background colour.




We have blend mode on elements too, but use mix-blend-mode for elements:


Further reading: https://css-tricks.com/basics-css-blend-modes/

Filters:
Only works on images, video and canvas. Like applying insta-style filters etc:



CSS shapes:
Still coming into browsers at the moment, a few quirks.
Eg. for styling text around shapes etc (like extra task from last week):

Further reading: https://www.html5rocks.com/en/tutorials/shapes/getting-started/
https://www.sarasoueidan.com/blog/css-shapes/

Custom properties:
(sort of) variables in CSS - the spec is just about to expand.

Need to use var every time you use
Still very new - so sass is better at this for now.
CSS variables are subject to the cascade and inherit their value from their parent. Custom properties do inherit. This means that if no value is set for a custom property on a given element, the value of its parent is used.
https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables

Maths
Again not fully supported, but can do maths with calc (different to sass)

https://css-tricks.com/a-couple-of-use-cases-for-calc/ 


 Cool CSS for class codepen




HW: CSS Complex Selectors
https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Selectors
https://www.smashingmagazine.com/2009/08/taming-advanced-css-selectors/ ⇒ 

https://learn.shayhowe.com/advanced-html-css/complex-selectors/ ⇒ 



Useful links

Useful
Talk of the day: The Power of CSS – Una Kravets / Front-Trends 2017
https://webdesign.tutsplus.com/courses/web-design-workflow-with-sass-and-compass
RJ codepens: https://codepen.io/Rumyra/pens/public/ 

Sass: https://sass-lang.com/guide

Sass presentation: https://gitpitch.com/develop-me/fellowship-wk2-adv-html-css?p=day08/01sass#/












