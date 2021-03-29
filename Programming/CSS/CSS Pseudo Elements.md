CSS Pseudo Elements 

# CSS Pseudo-elements

The CSS pseudo-elements is a ways to style elements of the document that weren't explicitly defined by a position in the document tree.

## What is Pseudo-element

The CSS pseudo-elements allow you to style the elements or parts of the elements without adding any IDs or classes to them. It will be really helpful in the situations when you just want to style the first letter of a paragraph to create the drop cap effect or you want to insert some content before or after an element, etc. only through style sheet.

CSS3 introduced a new double-colon (`::`) syntax for pseudo-elements to distinguish between them and pseudo-classes. The new syntax of the pseudo-element can be given with:

selector::pseudo-element { property: value; }

These are the following most commonly used pseudo-elements:

## The ::first-line Pseudo-element

The `::first-line` pseudo-element applies special style to the first line of a text.

The style rules in the following example formats the first line of text in a paragraph. The length of first line depends on the size of the browser window or containing element.

#### Example

```css
p::first-line {
    color: #ff0000;
    font-variant: small-caps;
}
```

**Note:** The CSS properties that can be applied to the `::first-line` pseudo-element are: [font properties](#), [background properties](#), [color](#), [word-spacing](#), [letter-spacing](#), [text-decoration](#), [vertical-align](#), [text-transform](#), [line-height](#).

* * *

## The ::first-letter Pseudo-element

The `::first-letter` pseudo-element is used to add a special style to the first letter of the first line of a text. The style rules in the following example formats the first letter of the paragraph of text and create the effect like drop cap.

#### Example

```css
p::first-letter {
    color: #ff0000;
    font-size: xx-large;
}
```

**Note:** The CSS properties that can be applied to the `::first-letter` pseudo-element are: [font properties](#), [text-decoration](#), [text-transform](#), [letter-spacing](#), [word-spacing](#), [line-height](#), [float](#), [vertical-align](#) (only if '[float](#)' is 'none'), [color](#), [margin](#) and [padding properties](#), [border properties](#), [background properties](#).

* * *

## The ::before and ::after Pseudo-element

The `::before` and `::after` pseudo-elements can be used to insert generated content either before or after an element's content. The [`content`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-content-property.php) CSS property is used in conjunction with these pseudo-elements, to insert the generated content.

This is very useful for further decorating an element with rich content that should not be part of the page's actual markup. You can insert regular strings of text or an embedded object such as image and other resources using these pseudo-elements.

#### Example

```css
h1::before {
    content: url("images/marker-left.gif");
}
h1::after {
    content: url("images/marker-right.gif");
}
```

* * *

## Pseudo-elements and CSS Classes

Generally we need to style only a certain paragraph of text or other [block-level](https://www.tutorialrepublic.com/css-tutorial/css-visual-formatting.php#block-level) elements with these pseudo-elements. That's where declaring a class to the pseudo-element comes into play. The pseudo-elements can be combined with the [CSS classes](https://www.tutorialrepublic.com/css-tutorial/css-selectors.php) to produce the effect particularly for the elements having that class.

The style rules in the following example will display the first letter of all paragraphs with the `class="article"`, in green and size of `xx-large`.

#### Example

```css
p.article::first-letter {
    color: #00ff00;
    font-size: xx-large;
}
```

* * *