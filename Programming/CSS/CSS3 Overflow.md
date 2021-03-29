CSS3 Overflow

# CSS3 Text Overflow

CSS3 new text properties provide more control over the text rendering.

## Handling Text Overflow in CSS3

CSS3 introduced several new property properties for modifing the text contents, however some of these properties are existed from a long time. These properties give you precise control over the rendering of text on the web browser.

## Hiding Overflow Text

Text can overflow, when it is prevented from wrapping, for example, if the value of [`white-space`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-white-space-property.php) property is set to `nowrap` for the containing element or a single word is too long to fit like a long email address. In such situation you can use the CSS3 [`text-overflow`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-text-overflow-property.php) property to determine how the overflowed text content will be displayed.

You can either display or clip the overflowed text or clip and display an ellipsis or a custom string in palace of the clipped text to indicate the user.

Values Accepted by the `word-break` property are: `clip` and `ellipsis` and `_string_`.

#### Example

```css
p {
    width: 400px;
    overflow: hidden;
    white-space: nowrap;
    background: #cdcdcd;
}
p.clipped {
    text-overflow: clip; /* clipped the overflowed text */
}
p.ellipses {
    text-overflow: ellipsis; /* display '…' to represent clipped text */
}
```

**Warning:** The `_string_` value for the `text-overflow` property is not supported in most of the web browsers, you should better avoid this.

* * *

## Breaking Overflow Text

You can also break a long word and force it to wrap onto a new line that overflows the boundaries of containing element using the CSS3 [`word-wrap`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-word-wrap-property.php) property.

Values Accepted by the `word-wrap` property are: `normal` and `break-word`.

#### Example

```css
p {
    width: 200px;
    background: #ffc4ff;
    word-wrap: break-word;
}
```

**Tip:** Please check out the individual property reference for all the possible values and the Browser support for these CSS properties.

* * *

## Specify Word Breaking Rules

You can also specify the line breaking rules for the text (i.e. how to break lines within words) yourself using the CSS3 [`word-break`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-word-break-property.php) property.

Values Accepted by the `word-break` property are: `normal`, `break-all` and `keep-all`.

#### Example

```css
p {
    width: 150px;
    padding: 10px;
}
p.break {
    background: #bedb8b;
    word-break: break-all;
}
p.keep {
    background: #f09bbb;
    word-break: keep-all;
}
```
* * *