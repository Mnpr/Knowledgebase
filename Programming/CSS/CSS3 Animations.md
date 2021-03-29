CSS3 Animations

# CSS3 Animations

The CSS3 animations feature allows you to create keyframe animations.

## Creating CSS3 Animations

In the previous chapter you've seen how to do simple animations like animating a property from one value to another via CSS3 transitions feature. However, the CSS3 transitions provide little control on how the animation progresses over time.

The CSS3 animations take it a step further with keyframe-based animations that allow you to specify the changes in CSS properties over time as a set of keyframes, like flash animations. Creating CSS animations is a two step process, as shown in the example below:

*   The first step of building a CSS animation is to defining individual keyframes and naming an animation with a keyframes declaration.
*   The second step is referencing the keyframes by name using the `animation-name` property as well as adding `animation-duration` and other optional [animation properties](#css3-animation-properties) to control the animation's behavior.

However, it is not necessary to define the keyframes rules before referencing or applying it. The following example will show you how to animate a [`<div>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-div-tag.php) box horizontally from one position to another using the CSS3 animation feature.

#### Example

```css
.box {
    width: 50px;
    height: 50px;
    background: red;
    position: relative;
    /* Chrome, Safari, Opera */
    -webkit-animation-name: moveit;
    -webkit-animation-duration: 2s;
    /* Standard syntax */
    animation-name: moveit;
    animation-duration: 2s;
}
 
/* Chrome, Safari, Opera */
@-webkit-keyframes moveit {
    from {left: 0;}
    to {left: 50%;}
}
 
/* Standard syntax */
@keyframes moveit {
    from {left: 0;}
    to {left: 50%;}
}
```

You must specify at least two properties `animation-name` and the `animation-duration` (greater than 0), to make the animation occur. However, all the other [animation properties](#css3-animation-properties) are optional, as their default values don't prevent an animation from happening.

**Note:** Not all CSS properties are animatable. In general, any CSS property that accepts values that are numbers, lengths, percentages, or colors is animatable.

* * *

## Defining Keyframes

Keyframes are used to specify the values for the animating properties at various stages of the animation. Keyframes are specified using a specialized [CSS at-rule](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-at-rules.php) — `@keyframes`. The keyframe selector for a keyframe style rule starts with a percentage (`%`) or the keywords `from` (same as 0%) or `to` (same as 100%). The selector is used to specify where a keyframe is constructed along the duration of the animation.

Percentages represent a percentage of the animation duration, 0% represents the starting point of the animation, 100% represents the end point, 50% represents the midpoint and so on. That means, a 50% keyframe in a 2s animation would be 1s into an animation.

#### Example

```css
.box {
    width: 50px;
    height: 50px;
    margin: 100px;
    background: red;
    position: relative;
    left: 0;
    /* Chrome, Safari, Opera */
    -webkit-animation-name: shakeit;
    -webkit-animation-duration: 2s;
    /* Standard syntax */
    animation-name: shakeit;
    animation-duration: 2s;
}
 
/* Chrome, Safari, Opera */
@-webkit-keyframes shakeit {
    12.5% {left: -50px;}
    25% {left: 50px;}
    37.5% {left: -25px;}
    50% {left: 25px;}
    62.5% {left: -10px;}
    75% {left: 10px;}
}
 
/* Standard syntax */
@keyframes shakeit {
    12.5% {left: -50px;}
    25% {left: 50px;}
    37.5% {left: -25px;}
    50% {left: 25px;}
    62.5% {left: -10px;}
    75% {left: 10px;}
}
```

* * *

## Animation Shorthand Property

There are many properties to consider when creating the animations. However, it is also possible to specify all the animations properties in one single property to shorten the code.

The `animation` property is a shorthand property for setting all the individual [animation properties](#css3-animation-properties) at once in the listed order. For example:

#### Example

```css
.box {
    width: 50px;
    height: 50px;
    background: red;
    position: relative;
    /* Chrome, Safari, Opera */
    -webkit-animation: repeatit 2s linear 0s infinite alternate;
    /* Standard syntax */
    animation: repeatit 2s linear 0s infinite alternate;
}
 
/* Chrome, Safari, Opera */
@-webkit-keyframes repeatit {
    from {left: 0;}
    to {left: 50%;}
}
 
/* Standard syntax */
@keyframes repeatit {
    from {left: 0;}
    to {left: 50%;}
}
```

**Note:** If any value is missing or not specified, the default value for that property will be used instead. That means, if the value for `animation-duration` property is missing, no transition will occur, because its default value is 0.

* * *

## CSS3 Animation Properties.

The following table provides a brief overview of all the animation-related properties.

| Property | Description |
| --- | --- |
| `[animation](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-animation-property.php)` | A shorthand property for setting all the animation properties in single declaration. |
| `[animation-name](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-animation-name-property.php)` | Specifies the name of `@keyframes` defined animations that should be applied to the selected element. |
| `[animation-duration](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-animation-duration-property.php)` | Specifies how many seconds or milliseconds that an animation takes to complete one cycle of the animation. |
| `[animation-timing-function](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-animation-timing-function-property.php)` | Specifies how the animation will progress over the duration of each cycle i.e. the easing functions. |
| `[animation-delay](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-animation-delay-property.php)` | Specifies when the animation will start. |
| `[animation-iteration-count](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-animation-iteration-count-property.php)` | Specifies the number of times an animation cycle should be played before stopping. |
| `[animation-direction](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-animation-direction-property.php)` | Specifies whether or not the animation should play in reverse on alternate cycles. |
| `[animation-fill-mode](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-animation-fill-mode-property.php)` | Specifies how a CSS animation should apply styles to its target before and after it is executing. |
| `[animation-play-state](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-animation-play-state-property.php)` | Specifies whether the animation is running or paused. |
| `[@keyframes](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css3-keyframes-rule.php)` | Specifies the values for the animating properties at various points during the animation. |
***