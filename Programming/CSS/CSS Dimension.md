CSS Dimension

# CSS Dimension

CSS dimension properties used to control the height and width of an element.

## CSS Dimension Properties

The CSS provides several properties such as `width`, `height`, `max-width` and `max-height` etc. that allows you to control the dimension of a box. The following section will describe you how to use these properties to create a better web page layout.

## The width and height Properties

The `width` and `height` property defines the width and height of the content area of an element. This width and height does not include paddings, borders, or margins. See the [CSS box model](https://www.tutorialrepublic.com/css-tutorial/css-box-model.php) to know how the effective width and height is calculated.

The `width` and `height` property can take values of a length (`px`, `pt`, `em`, etc.), a _percentage_, or the keyword `auto`. Negative length values are not allowed.

#### Example

```css
div {
    width: 300px;
    height: 200px;
}
```

This style rules assigns a fixed width of 300 pixels and height of 200px to the [`<div>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-div-tag.php) element.

**Note:** The special `auto` value allows the browsers to calculate the width automatically for the specified element. The _percentage (%)_ values refer to the width of the element's containing block.

* * *

## The max-height Property

The `max-height` property allows you to specify the maximum content height of a box. This maximum height does not include paddings, borders, or margins.

An element that has `max-height` applied will never be taller than the value specified, even if the `height` property is set to something larger. For example, if the `height` is set to 200px and the `max-height` set to 100px, the actual height of the element is 100px.

#### Example

```css
div {
    height: 200px;
    max-height: 100px;
}
```

The `max-height` property is usually used in conjunction with the `min-height` property to produce a height range for the element concerned.

**Note:** There is an exception to this rule — if the `min-height` property is specified with a value that is greater than that of `max-height` property, in this case the `min-height` value will in fact be the one that's applied.

* * *

## The min-height Property

The `min-height` property allows you to specify the minimum content height of a block. This minimum height doesn't include paddings, borders, or margins.

An element to which `min-height` is applied will never be smaller than the minimum height specified. For example, if the `height` is set to 200px, and the `min-height` is set to 300px, the actual height of the element is 300px.

#### Example

```css
div {
    height: 200px;
    min-height: 300px;
}
```

The `min-height` property is usually used in conjunction with the `max-height` property to produce a height range for the element concerned.

**Note:** The `min-height` property is usually used to ensure that an element has at least a minimum height even if no content is present. However the element will be allowed to grow normally if the content exceeds the minimum height set.

* * *

## The max-width Property

The `max-width` property allows you to specify the maximum content width of a block. This maximum width does not include paddings, borders, or margins.

An element to which a `max-width` is applied will never be wider than the value specified even if the width property is set to something larger. For example, if the `width` is set to 300px and the `max-width` is set to 200px, the actual width of the element will be 200px.

#### Example

```css
div {
    width: 300px;
    max-width: 200px;
}
```

The `max-width` property is often used in conjunction with the `min-width` property to produce a width range for the element concerned.

**Note:** There is an exception to this rule; if the `min-width` property is specified with a value greater than that of `max-width` property, in this case the `min-width` value will in fact be the one that's applied.

* * *

## The min-width Property

The `min-width` property allows you to specify the minimum content width of a block. This minimum width does not include paddings, borders, or margins.

An element to which `min-width` is applied will never be narrower than the minimum width specified. For example, if the `width` is set to 300px and the `min-width` is set to 400px, the actual width of the element is 400px.

#### Example

```css
div {
    width: 300px;
    min-width: 400px;
}
```

The `min-width` property is often used in conjunction with the `max-width` property to produce a width range for the element concerned.

**Note:** The `min-width` property is usually used to ensure that an element has at least a minimum width even if no content is present. However the element will be allowed to grow normally if its content exceeds the minimum width set.
* * *