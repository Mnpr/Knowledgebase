CSS3 Colors

# CSS3 Color

CSS3 provides several new ways to define a color values.

## Defining Colors in CSS3

In the previous section you've learnt how to define colors using the [color keywords and RGB notations](https://www.tutorialrepublic.com/css-tutorial/css-color.php). In addition to that CSS3 adds some new functional notations for setting color values for the elements which are `rgba()`, `hsl()` and `hsla()`.

In the following section we'll discuss about these color model one by one.

## RGBA Color Values

Colors can be defined in the RGBA model (red-green-blue-alpha) using the `rgba()` functional notation. RGBA color model are an extension of RGB color model with an alpha channel — which specifies the opacity of a color.

The alpha parameter accepts a value from `0.0` (fully transparent) to `1.0` (fully opaque).

#### Example

```css
h1 {
    color: rgba(0,0,255,0.5);
}
p {
    background-color: rgba(0%,0%,100%,0.3);
}
```

* * *

## HSL Color Values

Colors also can be defined the HSL model (hue-saturation-lightness) using the `hsl()` functional notation. Hue is represented as an angle (from `0` to `360`) of the color wheel or circle (i.e. the rainbow represented in a circle). This angle is given as a unit less number because the angle is so typically measured in degrees that the unit is implicit in CSS.

Saturation and lightness are represented as percentages. `100%` saturation means full color, and `0%` is a shade of gray. Whereas, `100%` lightness is white, `0%` lightness is black, and `50%` lightness is normal. Check out the example below:

#### Example

```css
h1 {
    color: hsl(360,70%,60%);
}
p {
    background-color: hsl(480,50%,80%);
}
```

**Tip:** By the definition `red=0=360`, and the other colors are spread around the circle, so `green=120`, `blue=240`, etc. As an angle, it implicitly wraps around such that `-120=240`, `480=120`, and so on.

* * *

## HSLA Color Values

Colors can be defined in the HSLA model (hue-saturation-lightness-alpha) using the `hsla()` functional notation. HSLA color model are an extension of HSL color model with an alpha channel — which specifies the opacity of a color.

The alpha parameter accepts a value from `0.0` (fully transparent) to `1.0` (fully opaque).

#### Example

```css
h1 {
    color: hsla(360,80%,50%,0.5);
}
p {
    background-color: hsla(480,60%,30%,0.3);
}
```

***