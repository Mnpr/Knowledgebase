CSS Selectors

# CSS Selectors

A CSS selector is a pattern to match the elements in an HTML document. The associated style rules is applied to the elements that match the selector pattern.

## What is Selector

Selectors are one of the most important aspects of CSS as they are used to select elements on a web page so that they can be styled. You can define selectors in various ways.

## Universal Selector

The universal selector, written as `*` i.e. asterisk or star symbol, matches every single element on the page. The universal selector may be omitted if other conditions exist on the target element. This selector is often used to remove the default margins and paddings from the elements for quick testing purpose.

#### Example

```css
* {
    margin: 0;
    padding: 0;
}
```

The style rules inside the `*` selector will be applied to every element in a document.

**Note:** It is not recommended to use the universal selector `*` in a production environment, since this selector matches every element on a page that puts too much of unnecessary pressure on the browsers.

* * *

## Element Type Selector

An element type selector matches every instance of the element in the document tree with the corresponding element type name.

#### Example

```css
p {
    color: blue;
}
```

The style rules inside the `p` selector will be applied on every `<p>` element in the document and color it blue, regardless of their position in the document tree.

* * *

## Id Selectors

The id selector is used to define style rules for a _single_ or _unique_ element.

The id selector is defined with a hash sign (`#`) immediately followed by the id value.

#### Example

```css
#error {
    color: red;
}
```

This style rule renders the text of an element in red, whose `id` attribute is set to `error`.

* * *

## Class Selectors

The class selectors can be used to select any HTML element that has a `class` attribute. All the elements having that class will be formatted according to the defined rule.

The class selector is defined with a period sign (`.`) immediately followed by the class value.

#### Example

```css
.blue {
    color: blue;
}
```

The above style rules renders the text in blue of every element in the document that has `class` attribute set to `blue`. You can make it a bit more particular. For example:

#### Example

```css
p.blue {
    color: blue;
}
```

The style rule inside the selector `p.blue` renders the text in blue of only those `<p>` elements that has `class` attribute set to `blue`, and has no effect on other paragraphs.

* * *

## Descendant Selectors

You can use these selectors when you need to select an element that is the descendant of another element. For example, if you want to target only those anchors that are contained within an unordered list, rather than targeting all anchor elements.

#### Example

```css
ul.menu li a {
    text-decoration: none;
}
h1 em {
    color: green;
}
```

The style rules inside the selector `ul.menu li a` applied to only those [`<a>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-links.php) i.e. anchor elements that contained inside an [unordered list](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-lists.php) having the class `.menu`, and has no effect on other links inside the document. Similarly, the style rules inside the `h1 em` selector applied to only [`<em>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-em-tag.php) elements that contained inside heading [`<h1>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-headings.php).

* * *

## Child Selectors

A child selector can be used to select only those elements that are the direct children of some element. A child selector is made up of two or more selectors separated by the greater than symbol (i.e. `>`). You can use these selectors for example, to select the first level of list elements inside a nested list that has more than one level.

#### Example

```css
ul > li {
    list-style: square;
}
ul > li ol {
    list-style: none;
}
```

The style rule inside the selector `ul > li` applied to only those `<li>` elements that are direct children of the `<ul>` elements, and has no effect on other list elements.

* * *

## Adjacent Sibling Selectors

The adjacent sibling selectors can be used to select sibling elements. This selector has the syntax like: E1 + E2, where E2 is the target of the selector.

The selector `h1 + p` in the example below will select the [`<p>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-paragraphs.php) elements only if both the [`<h1>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-headings.php) and `<p>` elements share the same parent in the document tree and `<h1>` is immediately precedes the `<p>` element. That means only those paragraphs that come immediately after each `<h1>` heading will have the associated style rules.

#### Example

```css
h1 + p {
    color: blue;
    font-size: 18px;
}
ul.task + p {
    color: #f0f;
    text-indent: 30px;
}
```

* * *

## General Sibling Selectors

The general sibling selector is similar to the adjacent sibling selector (E1 + E2), but it's less strict. A general sibling selector is made up of two simple selectors separated by the tilde (`∼`) character. It can be written like: E1 ∼ E2, where E2 is the target of the selector.

The selector `h1 ∼ p` in the example below will select all the `<p>` elements that preceded by the `<h1>` element, where all the elements share the same parent in the document tree.

#### Example

```css
h1 ∼ p {
    color: blue;
    font-size: 18px;
}
ul.task ∼ p {
    color: #f0f;
    text-indent: 30px;
}
```

There are more selectors like [attribute selectors](https://www.tutorialrepublic.com/css-tutorial/css-attribute-selectors.php), [pseudo-classes](https://www.tutorialrepublic.com/css-tutorial/css-pseudo-classes.php), [pseudo-elements](https://www.tutorialrepublic.com/css-tutorial/css-pseudo-elements.php). We will discuss about these selectors in upcoming chapters.

* * *

## Grouping Selectors

Often several selectors in a style sheet share the same style rules declarations. You can group them into a comma-separated list to minimize the code in your style sheet. It also prevents you from repeating the same style rules over and over again.

#### Example

```css
h1 {
    font-size: 36px;
    font-weight: normal;
}
h2 {
    font-size: 28px;
    font-weight: normal;
}
h3 {
    font-size: 22px;
    font-weight: normal;
}
```

As you can see in the above example, the same style rule `font-weight: normal;` is shared by the selectors `h1`, `h2` and `h3`. So, it can be grouped in a comma-separated list, like this:

#### Example

```css
h1, h2, h3 {
    font-weight: normal;
}
h1 {
    font-size: 36px;
}
h2 {
    font-size: 28px;
}
h3 {
    font-size: 22px;
}
```
* * *