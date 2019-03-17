# Sass File Structure

How you format your sass and files etc depends on how you like to break everything down ie by header/footer etc or much finer, by button, textbox etc (SMACSS)

Another example: https://www.sitepoint.com/architecture-sass-project/ 
sass/ 
| 
|– base/ 
|   |– _reset.scss       # Reset/normalize 
|   |– _typography.scss  # Typography rules 
|   ...                  # Etc… 
| 
|– components/ 
|   |– _buttons.scss     # Buttons 
|   |– _carousel.scss    # Carousel 
|   |– _cover.scss       # Cover 
|   |– _dropdown.scss    # Dropdown 
|   |– _navigation.scss  # Navigation 
|   ...                  # Etc… 
| 
|– helpers/ 
|   |– _variables.scss   # Sass Variables 
|   |– _functions.scss   # Sass Functions 
|   |– _mixins.scss      # Sass Mixins 
|   |– _helpers.scss     # Class & placeholders helpers 
|   ...                  # Etc… 
| 
|– layout/ 
|   |– _grid.scss        # Grid system 
|   |– _header.scss      # Header 
|   |– _footer.scss      # Footer 
|   |– _sidebar.scss     # Sidebar 
|   |– _forms.scss       # Forms 
|   ...                  # Etc… 
| 
|– pages/ 
|   |– _home.scss        # Home specific styles 
|   |– _contact.scss     # Contact specific styles 
|   ...                  # Etc… 
| 
|– themes/ 
|   |– _theme.scss       # Default theme 
|   |– _admin.scss       # Admin theme 
|   ...                  # Etc… 
| 
|– vendors/ 
|   |– _bootstrap.scss   # Bootstrap 
|   |– _jquery-ui.scss   # jQuery UI 
|   ...                  # Etc… 
| 
| 
`– main.scss             # primary Sass file

And another example: https://medium.com/@dannyhuang_75970/sass-project-structure-for-big-projects-8c4a740846ee 

## Bigger Projects
For a bigger project, multiple page app, I use 7–1 pattern, it is similar to the small project file structure but with more folders. Here’s what 7–1 the pattern looks like.
base/
components/
layout/
pages/
themes/
abstracts/
vendors/
main.scss

The base, components, and layout do the same job as the file structure above. However, instead of a single file, we now manage them in a folder.

**Base**: animations, base, typography, and utilies.
Components: have a single scss file for each individual component

**Layout**: Header, footer, grid, navigation
Pages: Have a single scss for each specific page
Themes: deals with various themes (optional, I haven’t use it yet)

**Abstracts**: handles function, mixins, and variables
Vendor: handles 3rd party css

Here’s a boilerplate from the original author.
HugoGiraudel/sass-boilerplate
sass-boilerplate - A boilerplate for Sass projects using the 7-1 architecture pattern from Sass Guidelines.github.com

Resource:
Sass Guidelines: https://sass-guidelin.es/


⇒ The 7-1 method by Hugo Giraudel
https://scotch.io/tutorials/aesthetic-sass-1-architecture-and-style-organization



### Organising your sass files
No right/wrong. You can organise the sass files into folders:


NB. style.css.map is a Chrome thing, helpful for inspecting the page in Chrome. Leave in the main folder.

If moving files into subfolders, make sure to put in the correct path when using @import:


## File structure:
Most major CSS architectures -- including SMACSS, OOCSS, and Atomic Design -- emphasize the importance of modularity, or viewing your UI as a collection of components.
Generally speaking, components are reusable, self-contained, independent units of a user interface. Components may be composed of other components, such as a search form (composed of a text input and a button), and they may have variants, such as a smaller or different color buttons.

Getting up and going with an overall file structure for your project is a relatively easy task, and the style organization within each component stylesheet will ensure that components are flexible enough to adapt to any theme and fit cohesively with all of the other components. This is the key to having an aesthetic look and feel in your website or web app. A non-trivial, well-structured component will include most of the following component-specific parts:

**Variables** - for relating component-specific values to others and preventing magic numbers
**Mixins** - for dynamically generating variations of the component (not necessary if few variations exist)
**Structure** - the CSS component layout/structure, excluding any non-layout rules, such as color
**Relationships** - any component-specific CSS with regard to relationships (via combinators) with other components
**Themes** - thematic CSS for non-layout component styling, such as background, colors, shadows, etc.
**Exported Selectors** - the manifested CSS classes/selectors, if they are to be expose
https://scotch.io/tutorials/aesthetic-sass-1-architecture-and-style-organization

NB. sass comments = // (like JS). Can also use CSS style comments /**/, but only the CSS comments will show when compiled, not the // ones.

## Sass partials
A partial is simply a Sass file named with a leading underscore. You might name it something like _partial.scss . The underscore lets Sass know that the file is only a partial file and that it should not be generated into a CSS file. Sass partials are used with the @import directive.
https://sass-lang.com/guide