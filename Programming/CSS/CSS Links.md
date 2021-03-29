CSS Links

# CSS Links

A link or hyperlink is a connection from one web resource to another.

## Styling Links with CSS

A link has four different states — `link`, `visited`, `active` and `hover`. These four states of a link or hyperlink can be styled differently through CSS properties using the [pseudo-classes](https://www.tutorialrepublic.com/css-tutorial/css-pseudo-classes.php) of anchor element, depending on what state they are in.

Here're the CSS pseudo-classes associated with HTML [`<a>`](https://www.tutorialrepublic.com/html-reference/html-a-tag.php) tag that you can use to define the different styles for the different states of a hyperlink.

*   **a:link** — Set styles for a normal or unvisited links that has no mouse pointer over it.
*   **a:visited** — Set styles for a link the user has visited but has no mouse pointer on it.
*   **a:hover** — Set styles for a link when the user place the mouse pointer over it.
*   **a:active** — Set styles for a link that is in the process of being clicked.

You can specify any CSS property you'd like e.g. [`color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-color-property.php), [`font-family`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-font-family-property.php), [`background`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-property.php), etc. to each of these [selectors](https://www.tutorialrepublic.com/css-tutorial/css-selectors.php) to redefine the style of links, just like you'd do with the normal text.

#### Example

```css
a:link {    /* unvisited link */
    color: #FF0000;
    text-decoration: none;
}
a:visited {    /* visited link */
    color: #00FF00;
}
a:hover {    /* mouse over link */
    color: #FF00FF;
    text-decoration: underline;
}
a:active {    /* active link */
    color: #0000FF;
}
```

The order in which you are setting the style for several link states is important, as what defines last takes precedence over the earlier CSS code.

**Note:** The order of the pseudo classes should be the following: `:link`, `:visited`, `:hover`, `:active`, `:focus` in order for these to work properly.

* * *

## Standard Link Styles

In all major web browsers, links on the web pages have underlines and use the browser's default link colors, if you don't set the styles specifically for them.

For instance, the default link colors in Gecko based web browsers like Firefox are — blue for unvisited, purple for visited and red for the active link.

## Setting the Color of Links

Following is the example which demonstrates how to set the link color.

#### Example

```css
a:link {    /* unvisited link */
    color: #FF0000;
}
a:visited {    /* visited link */
    color: #00FF00;
}
a:hover {    /* mouse over link */
    color: #FF00FF;
}
a:active {    /* active link */
    color: #0000FF;
}
```

## Removing the Default Underline from Links

The [`text-decoration`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-text-decoration-property.php) CSS property is generally used to remove the default underlines from links. The following example demonstrates how to remove or set the `text-decoration` property for the different states of a hyperlink.

#### Example

```css
a:link {    /* unvisited link */
    color: #FF0000;
    text-decoration: none;
}
a:visited {    /* visited link */
    color: #00FF00;
    text-decoration: none;
}
a:hover {    /* mouse over link */
    color: #FF00FF;
    text-decoration: underline;
}
a:active {    /* active link */
    color: #0000FF;
    text-decoration: underline;
}
```
* * *