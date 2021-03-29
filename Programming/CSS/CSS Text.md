CSS Text

# CSS Text

CSS text properties allow you to define several text styles such as color, alignment, spacing, decoration, transformation etc. very easily an effectively.

## Formatting Text with CSS

CSS has several properties for defining the styles of text. These properties give you precise control over the visual appearance of the _characters_, _spaces_, _words_, _paragraphs_, etc.

You can set following text properties of an element:

## Text Color

Text color is defined by the CSS [`color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-color-property.php) property. [Learn more.](https://www.tutorialrepublic.com/css-tutorial/css-color.php)

#### Example

```css
h1 {
    color: #ff0000;
}
p {
    color: green;
}
```

**Note:** Although, the color of the text seems like it would be a part of the CSS text, but it is actually a standalone property in CSS.

* * *

## Text Alignment

The [`text-align`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-text-align-property.php) property is used to set the horizontal alignment of a text.

Possible values for this property are: `left`, `right`, `center`, `justify`, and [`inherit`](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#inherit).

#### Example

```css
h1 {
    text-align: center;
}
p {
    text-align: justify;
}
```

**Note:** When `text-align` is set to `justify`, each line is stretched so that every line has equal width, and the left and right margins are straight.

* * *

## Text Decoration

The [`text-decoration`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-text-decoration-property.php) property is used to set or remove decorations from text.

Possible values of this property are: `none`, `underline`, `overline`, `line-through`, `blink` and [`inherit`](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#inherit). You should avoid underline text that is not a link, as it might confuse the visitor.

#### Example

```css
h1 {
    text-decoration: overline;
}
h2 {
    text-decoration: line-through;
}
h3 {
    text-decoration: underline;
}
```

**Warning:** The `blink` value for the CSS `text-decoration` property is not supported by the most of the browsers. You should avoid this value.

* * *

## Removing the Links Default Underlines

The `text-decoration` property is commonly used to remove the default underlines from the hyperlinks. Removing the underline completely can confuse the visitor. Unless you provide some other visual cues to make it stands out, while styling the links.

For example, you can use dots to underline your links instead of a solid line.

#### Example

```css
a {
    text-decoration: none;
    border-bottom: 1px dotted;
}
```

**Note:** When you create an [HTML link](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-links.php), browsers built in style sheet automatically underline it, so that the readers can see what text is clickable.

* * *

## Text Transformation

The `text-transform` property is used to set the cases for a text.

It can be used to set the element's text content into uppercase or lowercase letters, or capitalize the first letter of each word. Possible values for the `text-transform` property are: `none`, `capitalize`, `uppercase`, `lowercase` and [`inherit`](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#inherit).

#### Example

```css
p.up {
    text-transform: uppercase;
}
p.cap {
    text-transform: capitalize;
}
p.low {
    text-transform: lowercase;
}
```

* * *

## Text Indentation

The `text-indent` property is used to set the indentation of the first line of text of an element. Possible values for the `text-indent` property are: _percentage_ (`%`), _length_ (specifying indent space) or [`inherit`](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#inherit).

The following example demonstrates how to indent the first line of a paragraph.

#### Example

```css
p {
    text-indent: 100px;
}
```

**Note:** Whether the text is indented from the left or from the right depends on the direction of text inside the element, defined by the CSS [`direction`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-direction-property.php) property.

* * *

## Word Spacing

The `word-spacing` property used to sets the spacing between the words.

*   Word spacing can be affected by text justification. See the [`text-align`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-text-align-property.php) property.
*   When whitespace is preserved all space characters are affected by the word spacing. See the CSS [`white-space`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-white-space-property.php) property.

Possible values for the `word-spacing` property are: _length_ (specifying the space to be inserted between words), `normal` and [`inherit`](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#inherit).

#### Example

```css
p.one {
    word-spacing: 20px;
}
p.two {
    word-spacing: 20px;
    text-align: justify;
}
p.three {
    word-spacing: 20px;
    white-space: pre;
}
```

* * *

## Letter Spacing

The [`letter-spacing`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-letter-spacing-property.php) property is used to set extra spacing between the characters of text.

Possible values for this property are: _length_ (specifying the extra space to be inserted between characters in addition to the default inter-character space), `normal` and [`inherit`](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#inherit).

#### Example

```css
h1 {
    letter-spacing: -3px;
}
p {
    letter-spacing: 10px;
}
```

* * *

## Line Height

The [`line-height`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-line-height-property.php) property defines height (also called _leading_) of a line of text.

Possible values for this property are: _percentage_ (`%`), _length_, _number_, `normal` and [`inherit`](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#inherit).

#### Example

```css
p {
    line-height: 1.2;
}
```

When the value is a number, the line height is calculated by multiplying the element's font size by the number. While, percentage values are relative to the element's font size.

**Note:** Negative values for this property are not allowed. This property is also a component of the [font shorthand property](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-font-property.php).

If the value of the `line-height` property is greater than the value of the [`font-size`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-font-size-property.php) for an element, this difference (called the _"leading"_) is cut in half (called the _"half-leading"_) and distributed evenly on the top and bottom of the in-line box.

#### Example

```css
p {
    font-size: 14px;
    line-height: 20px;
    background-color: #f0e68c;
}
```

To learn more about text styling see [font](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-font-property.php) and [text-related](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-text-align-property.php) properties.
* * *