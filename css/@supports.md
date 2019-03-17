# @Supports

The @supports CSS rule lets you specify declarations that depend on a browser's support for one or more specific CSS features. This is called a feature query. The rule may be placed at the top level of your code or nested inside any other conditional group at-rule.

```css
@supports (display: grid) {
  div {
    display: grid;
  }
}
@supports not (display: grid) {
  div {
    float: right;
  }
}
```
In JavaScript, @supports can be accessed via the CSS object model interface CSSSupportsRule.


[@supports \| MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports)
