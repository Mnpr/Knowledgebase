CSS Pseudo Classes 

# CSS Pseudo-classes

A CSS pseudo-class selector matches components based on an additional condition and not necessarily defined by the document tree.

## What is Pseudo-class

The CSS pseudo-classes allow you to style the dynamic states of an element such as hover, active and focus state, as well as elements that are existing in the document tree but can't be targeted via the use of other selectors without adding any IDs or classes to them, for example, targeting the first or last child elements.

A pseudo-class starts with a colon (`:`). Its syntax can be given with:

selector:pseudo-class { property: value; }

The following section describes the most commonly used pseudo-classes.

## Anchor Pseudo-classes

Using [anchor](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-a-tag.php) pseudo-classes links can be displayed in different ways:

These pseudo-classes let you style unvisited links differently from visited ones. The most common styling technique is to remove underlines from visited links.

#### Example

```css
a:link {
    color: blue;
}
a:visited {
    text-decoration: none;
}
```

Some anchor pseudo-classes are dynamic — they're applied as a result of user interaction with the document like on hover, or on focus etc.

#### Example

```css
a:hover {
    color: red;
}
a:active {
    color: gray;
}
a:focus {
    color: yellow;
}
```

These pseudo-classes change how the links are rendered in response to user actions.

*   `:hover` applies when a user places cursor over the element, but does not select it.
*   `:active` applies when the element is activated or clicked.
*   `:focus` applies when the element has keyboard focus.

**Note:** To make these pseudo-classes work perfectly, you must define them in the exact order — `:link`, `:visited`, `:hover`, `:active`, `:focus`.

* * *

## The :first-child Pseudo-class

The `:first-child` pseudo-class matches an element that is the first child element of some other element. The selector `ol li:first-child` in the example below select the first list item of an ordered list and removes the top border form it.

#### Example

```css
ol li:first-child {
    border-top: none;
}
```

**Note:** To make `:first-child` to work in Internet Explorer 8 and earlier versions, a [`<!DOCTYPE>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-doctypes.php) must be declared at the top of document.

* * *

## The :last-child Pseudo-class

The `:last-child` pseudo-class matches an element that is the last child element of some other element. The selector `ul li:last-child` in the example below select the last list item from an unordered list and removes the right border from it.

#### Example

```css
ul li:last-child {
    border-right: none;
}
```

**Note:** The CSS `:last-child` selector does not work in Internet Explorer 8 and earlier versions. Supports in Internet Explorer 9 and above.

* * *

## The :nth-child Pseudo-class

The CSS3 introduces a new `:nth-child` pseudo-class that allows you to target one or more specific children of a given parent element. The basic syntax of this selector can be given with `:nth-child(N)`, where `N` is an argument, which can be a number, a keyword (`even` or `odd`), or an expression of the form `xn+y` where `x` and `y` are integers (e.g. `1n`, `2n`, `2n+1`, …).

#### Example

```css
table tr:nth-child(2n) td {
    background: #eee;
}
```

The style rules in the example above simply highlight the alternate table row, without adding any IDs or classes to the [`<table>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-tables.php) elements.

**Tip:** The CSS `:nth-child(N)` selector is very useful in the situations where you have to select the elements that appears inside the document tree in a specific interval or pattern like at even or odd places, etc.

* * *

## The :lang Pseudo-class

The language pseudo-class `:lang` allows constructing selectors based on the language setting for specific tags. The `:lang` pseudo-class in the example below defines the quotation marks for [`<q>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-q-tag.php) elements that are explicitly given a language value of `no`.

#### Example

```css
q:lang(no) {
    quotes: "~" "~";
}
/* HTML code snippet */
<p>Some text <q lang="no">A quote in a paragraph</q> Some text.</p>
```

**Note:** Internet Explorer up to version 7 does not support the `:lang` pseudo-class. IE8 supports only if a [`<!DOCTYPE>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-doctypes.php) is specified.

* * *

## Pseudo-classes and CSS Classes

Pseudo-classes can be combined with CSS classes.

The link with `class="red"`, in the example below will be displayed in red.

#### Example

```css
a.red:link {    /* style rule */
    color: #ff0000;
}
<a class="red" href="#">Click me</a>    /* HTML code snippet */
```
* * *