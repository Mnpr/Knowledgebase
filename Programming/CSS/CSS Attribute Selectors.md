CSS Attribute Selectors

# CSS Attribute Selectors

An attribute selector selects the HTML elements that has a specific attribute or attribute with a specified value.

## Understanding the Attribute Selectors

The CSS attribute selectors provides an easy and powerful way to apply the styles on HTML elements based on the presence of a particular [attribute or attribute value](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-attributes.php).

You can create an attribute selector by putting the attribute—optionally with a value—in a pair of square brackets. You can also place an [element type selector](https://www.tutorialrepublic.com/css-tutorial/css-selectors.php) before it.

The following sections describe the most common attribute selectors.

## CSS \[attribute\] Selector

This is the simplest form of an attribute selector that applies the style rules to an element if a given attribute exists. For example, we can style all the elements that have a `title` attribute by using the following style rules:

#### Example

```css
[title] {
    color: blue;
}
```

The selector `[title]` in the above example matches all elements that has a `title` attribute.

You can also restrict this selection to a particular HTML element by placing the attribute selector after an element type selector, like this:

#### Example

```css
abbr[title] {
    color: red;
}
```

The selector `abbr[title]` matches only [`<abbr>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-abbr-tag.php) elements that has a `title` attribute, so it matches the abbreviation, but not the [anchor](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-a-tag.php) elements having `title` attribute.

* * *

## CSS \[attribute="value"\] Selector

You can use the `=` operator to make an attribute selector matches any element whose attribute value is exactly equal to the given value:

#### Example

```css
input[type="submit"] {
    border: 1px solid green;
}
```

The selector in the above example matches all [`<input>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-input-tag.php) element that has a `type` attribute with a value equal to `submit`.

* * *

## CSS \[attribute~="value"\] Selector

You can use the `~=` operator to make an attribute selector matches any element whose attribute value is a list of _space-separated_ values (like `class="alert warning"`) , one of which is exactly equal to the specified value:

#### Example

```css
[class~="warning"] {
    color: #fff;
    background: red;
}
```

This selector matches any HTML element with a `class` attribute that contains space-separated values, one of which is `warning`. For example, it matches the elements having the class values `warning`, `alert warning` etc.

* * *

## CSS \[attribute|="value"\] Selector

You can use the `|=` operator to make an attribute selector matches any element whose attribute has a _hyphen-separated_ list of values beginning with the specified value:

#### Example

```css
[lang|=en] {
    color: #fff;
    background: blue;
}
```

The selector in the above example matches all elements that has an [`lang`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-common-attributes.php) attribute containing a value start with `en`, whether or not that value is followed by a hyphen and more characters. In other words, it matches the elements with `lang` attribute that has the values `en`, `en-US`, `en-GB`, and so on but not `US-en`, `GB-en`.

* * *

## CSS \[attribute^="value"\] Selector

You can use the `^=` operator to make an attribute selector matches any element whose attribute value _starts with_ a specified value. It does not have to be a whole word.

#### Example

```css
a[href^="http://"] {
    background: url("external.png") 100% 50% no-repeat;
    padding-right: 15px;
}
```

The selector in the example above will target all external links and add a small icon indicating that they will open in a new tab or window.

* * *

## CSS \[attribute$="value"\] Selector

Similarly, you can use the `$=` operator to select all elements whose attribute value _ends with_ a specified value. It does not have to be a whole word.

#### Example

```css
a[href$=".pdf"] {
    background: url("pdf.png") 0 50% no-repeat;
    padding-left: 20px;
}
```

The selector in the example above select all [`<a>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-a-tag.php) elements that links to a PDF document and add a small PDF icon to provide hints to the user about the link.

* * *

## CSS \[attribute*="value"\] Selector

You can use the `*=` operator to make an attribute selector matches all elements whose attribute value contains a specified value.

#### Example

```css
[class*="warning"] {
    color: #fff;
    background: red;
}
```

This selector in the example above matches all HTML elements with a `class` attribute that values contains `warning`. For example, it matches the elements having class values `warning`, `alert warning`, `alert-warning` or `alert_warning` etc.

* * *

## Styling Forms with Attribute Selectors

The attribute selectors are particularly useful for styling forms without [`class`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-common-attributes.php) or [`id`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-common-attributes.php):

#### Example

```css
input[type="text"], input[type="password"] {
    width: 150px;
    display: block;
    margin-bottom: 10px;
    background: yellow;
}
input[type="submit"] {
    padding: 2px 10px;
    border: 1px solid #804040;
    background: #ff8040;
}
```
* * *