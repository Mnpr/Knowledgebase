CSS3 Multi-Column Layouts

# CSS3 Multi-Column Layouts

With CSS3, you can split the text content of an element in multiple columns.

## Creating Multi-Column Layouts

The CSS3 has introduced the multi-column layout module for creating multiple column layouts in an easy and efficient way. Now you can create layouts like you see in magazines and newspapers without using the floating boxes. Here is a simple example of splitting some text into three columns using the CSS3 multiple column layout feature.

#### Example

```css
p {
    -webkit-column-count: 3; /* Chrome, Safari, Opera */
       -moz-column-count: 3; /* Firefox */
            column-count: 3; /* Standard syntax */
}
```

* * *

## Setting Column Count or Width

The CSS properties `column-count` and `column-width` control whether and how many columns will appear. The `column-count` property sets the number of columns inside the multicol element, whereas the `column-width` property sets the desired width of the columns.

#### Example

```css
p {
    -webkit-column-width: 150px; /* Chrome, Safari, Opera */
       -moz-column-width: 150px; /* Firefox */
            column-width: 150px; /* Standard syntax */
}
```

**Note:** The `column-width` describes the optimal width of the column. However, the actual column width may be wider or narrower according to the space available. This property should not be used with the `column-count` property.

* * *

## Setting Column Gap

You can control the gap between columns using the `column-gap` property. The same gap is applied between each column. The default gap is normal which is equivalent to `1em`.

#### Example

```css
p {
    /* Chrome, Safari, Opera */
    -webkit-column-count: 3;
    -webkit-column-gap: 100px;
    /* Firefox */
    -moz-column-count: 3;
    -moz-column-gap: 100px;
    /* Standard syntax */
    column-count: 3;
    column-gap: 100px;
}
```

* * *

## Setting Column Rules

You can also add a line between the columns i.e. the rule using the `column-rule` property. It is a shorthand property for setting width, style, and color of the rule in a single declaration. The `column-rule` property takes the same values as border and outline.

#### Example

```css
p {
    /* Chrome, Safari, Opera */
    -webkit-column-count: 3;
    -webkit-column-gap: 100px;
    -webkit-column-rule: 2px solid red;
    /* Firefox */
    -moz-column-count: 3;
    -moz-column-gap: 100px;
    -moz-column-rule: 2px solid red;
    /* Standard syntax */
    column-count: 3;
    column-gap: 100px;
    column-rule: 2px solid red;
}
```

**Note:** The width of column rule does not affect the width of column boxes, but if a column rule is wider than the gap, the adjacent column boxes will overlap the rule.

* * *

## CSS3 Multiple Columns Properties

The following table provides a brief overview of all the multiple columns properties:

| Property | Description |
| --- | --- |
| `[column-count](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-count-property.php)` | Specifies the number of columns inside a multi-column element. |
| `[column-fill](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-fill-property.php)` | Specifies how content is spread across columns. |
| `[column-gap](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-gap-property.php)` | Specifies the gap between the columns. |
| `[column-rule](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-rule-property.php)` | Specifies a straight line or rule, to be drawn between each column. |
| `[column-rule-color](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-rule-color-property.php)` | Specifies the color of the rule between columns. |
| `[column-rule-style](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-rule-style-property.php)` | Specifies the style of the rule between columns. |
| `[column-rule-width](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-rule-width-property.php)` | Specifies the width of the rule between columns. |
| `[column-span](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-span-property.php)` | Specifies how many columns an element spans across. |
| `[column-width](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-width-property.php)` | Specifies the optimal width of the columns. |
| `[columns](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-columns-property.php)` | A shorthand property for setting both the [`column-width`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-width-property.php) and the [`column-count`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-column-count-property.php) properties at the same time. |

* * *