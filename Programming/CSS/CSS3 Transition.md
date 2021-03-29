CSS3 Transition

# CSS3 Transitions

The CSS3 transition feature allows the changes in CSS property values to occur smoothly over a specified duration.

## Understanding CSS3 Transitions

Normally when the value of a CSS property changes, the rendered result is instantly updated. A common example is changing the background color of a button on mouse hover. In a normal scenario the background color of the button is changes immediately from the old property value to the new property value when you place the cursor over the button.

CSS3 introduces a new transition feature that allows you to animate a property from the old value to the new value smoothly over time. The following example will show you how to animate the [`background-color`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-background-color-property.php) of an HTML button on mouse hover.

#### Example

```css
button {
    background: #fd7c2a;
    /* For Safari 3.0+ */
    -webkit-transition-property: background;
    -webkit-transition-duration: 2s;
    /* Standard syntax */
    transition-property: background;
    transition-duration: 2s;
}
button:hover {
    background: #3cc16e;
}
```

To make the transition occur, you must specify at least two things — the name of the CSS property to which you want to apply the transition effect using the `transition-property` CSS property, and the duration of the transition effect (greater than 0) using the `transition-duration` CSS property. However, all the other [transition properties](#transition-properties) are optional, as their default values don't prevent a transition from happening.

**Note:** Not all CSS properties are animatable. In general, any CSS property that accepts values that are numbers, lengths, percentages, or colors is animatable.

* * *

## Performing Multiple Transitions

Each of the transition properties can take more than one value, separated by commas, which provides an easy way to define multiple transitions at once with different settings.

#### Example

```css
button {
    background: #fd7c2a;
    border: 3px solid #dc5801;
    /* For Safari 3.0+ */
    -webkit-transition-property: background, border;
    -webkit-transition-duration: 1s, 2s;
    /* Standard syntax */
    transition-property: background, border;
    transition-duration: 1s, 2s;
}
button:hover {
    background: #3cc16e;
    border-color: #288049;
}
```

* * *

## Transition Shorthand Property

There are many properties to consider when applying the transitions. However, it is also possible to specify all the transition properties in one single property to shorten the code.

The `transition` property is a shorthand property for setting all the individual transition properties (i.e., `transition-property`, `transition-duration`, `transition-timing-function`, and `transition-delay`) at once in the listed order.

It's important to stick to this order for the values, when using this property.

#### Example

```css
button {
    background: #fd7c2a;
    -webkit-transition: background 2s ease-in 0s; /* For Safari 3.0+ */
    transition: background 2s ease-in 0s; /* Standard syntax */
}
button:hover {
    background: #3cc16e;
}
```

**Note:** If any value is missing or not specified, the default value for that property will be used instead. That means, if the value for `transition-duration` property is missing, no transition will occur, because its default value is 0.

* * *

## CSS3 Transition Properties

The following table provides a brief overview of all the transition properties:

| Property | Description |
| --- | --- |
| `[transition](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-transition-property.php)` | A shorthand property for setting all the four individual transition properties in a single declaration. |
| `[transition-delay](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-transition-delay-property.php)` | Specifies when the transition will start. |
| `[transition-duration](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-transition-duration-property.php)` | Specifies the number of seconds or milliseconds a transition animation should take to complete. |
| `[transition-property](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-transition-property-property.php)` | Specifies the names of the CSS properties to which a transition effect should be applied. |
| `[transition-timing-function](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-transition-timing-function-property.php)` | Specifies how the intermediate values of the CSS properties being affected by a transition will be calculated. |

* * *