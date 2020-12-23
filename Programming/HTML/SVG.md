SVG 


# HTML5 SVG

The Scalable Vector Graphics (SVG) is an XML-based image format that is used to define two-dimensional vector based graphics for the web. Unlike raster image (e.g. `.jpg`, `.gif`, `.png`, etc.), a vector image can be scaled up or down to any extent without losing the image quality.

An SVG image is drawn out using a series of statements that follow the XML schema — that means SVG images can be created and edited with any text editor, such as Notepad. There are several other advantages of using SVG over other image formats like JPEG, GIF, PNG, etc.

*   SVG images can be searched, indexed, scripted, and compressed.
*   SVG images can be created and modified using JavaScript in real time.
*   SVG images can be printed with high quality at any resolution.
*   SVG content can be animated using the built-in animation elements.
*   SVG images can contain [hyperlinks](https://www.tutorialrepublic.com/html-tutorial/html-links.php) to other documents.

**Tip:** The vector images are composed of a fixed set of shapes defined by math, while the bitmap or raster images are composed of a fixed set of dots called pixels.

* * *

## Embedding SVG into HTML Pages

You can embed SVG graphics directly into your document using the HTML5 `<svg>` element.

Let's take a look at the following example to understand how it basically works:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Embedding SVG in HTML</title>
</head>
<body>
    <svg width="300" height="200">
        <text x="10" y="20" style="font-size:14px;">
            Your browser support SVG.
        </text>
        Sorry, your browser does not support SVG.
    </svg>
</body>
</html>
```

**Note:** All the major modern web browsers like Chrome, Firefox, Safari, and Opera, as well as Internet Explorer 9 and above support inline SVG rendering.

* * *

## Drawing Path and Shapes with SVG

The following section will explain you how to draw basic vector-based paths and shapes on the web pages using the newly introduced HTML5 `<svg>` element.

## Drawing a Line

The most basic path you can draw with SVG is a straight line. The following example will show you how to create a straight line using the SVG `<line>` element:

#### Example

```markup
<svg width="300" height="200">
    <line x1="50" y1="50" x2="250" y2="150" style="stroke:red; stroke-width:3;" />
</svg>
```

The attributes `x1`, `x2`, `y1` and `y2` of the `<line>` element draw a line from `(x1,y1)` to `(x2,y2)`.

* * *

## Drawing a Rectangle

You can create simple rectangle and square shapes using the SVG `<rect>` element. The following example will show you how to create and style a rectangular shape with SVG:

#### Example

```markup
<svg width="300" height="200">
    <rect x="50" y="50" width="200" height="100" style="fill:orange; stroke:black; stroke-width:3;" />
</svg>
```

The attributes `x` and `y` of `<rect>` element defines the co-ordinates of the top-left corner of the rectangle. The attributes `width` and `height` specifies the width and height of the shape.

* * *

## Drawing a Circle

You can also create the circle shapes using the SVG `<circle>` element. The following example will show you how to create and style a circular shape with SVG:

#### Example

```markup
<svg width="300" height="200">
    <circle cx="150" cy="100" r="70" style="fill:lime; stroke:black; stroke-width:3;" />
</svg>
```

The attributes `cx` and `cy` of the `<circle>` element defines the co-ordinates of the center of the circle and the attribute `r` specifies the radius of the circle. However, if the attributes `cx` and `cy` are omitted or not specified, the center of the circle is set to `(0,0)`.

* * *

## Drawing Text with SVG

You can also draw text on the web pages with SVG. The text in SVG is rendered as a graphic so you can apply all the graphic transformation to it but it is still acts like text — that means it can be selected and copied as text by the user. Let's try an example to see how this works:

#### Example

```markup
<svg width="300" height="200">
    <text x="20" y="30" style="fill:purple; font-size:22px;">
        Welcome to Our Website!
    </text>
    <text x="20" y="30" dx="0" dy="20" style="fill:navy; font-size:14px;">
        Here you will find lots of useful information.
    </text>
</svg>
```

The attributes `x` and `y` of the `<text>` element defines the location of the top-left corner in absolute terms whereas the attributes `dx` and `dy` specifies the relative location.

You can even use the `<tspan>` element to reformat or reposition the span of text contained within a `<text>` element. Text contained in separate tspans, but inside the same text element can all be selected at once — when you click and drag to select the text. However, the text in separate text elements cannot be selected at the same time. Let's check out an example:

#### Example

```markup
<svg width="300" height="200">
    <text x="30" y="15" style="fill:purple; font-size:22px; transform:rotate(30deg);">
        <tspan style="fill:purple; font-size:22px;">
            Welcome to Our Website!
        </tspan>
        <tspan dx="-230" dy="20" style="fill:navy; font-size:14px;">
            Here you will find lots of useful information.
        </tspan>
    </text>
</svg>
```

* * *

## Differences between SVG and Canvas

The HTML5 introduced the two new graphical elements `<canvas>` and `<svg>` for creating rich graphics on the web, but they are fundamentally different.

The following table summarizes some of the basic differences between these two elements, which will help you to understand how to use these elements effectively and appropriately.

| SVG | Canvas |
| --- | --- |
| Vector based (composed of shapes) | Raster based (composed of pixel) |
| Multiple graphical elements, which become the part of the page's DOM tree | Single element similar to [`<img>`](https://www.tutorialrepublic.com/html-reference/html-img-tag.php) in behavior. Canvas diagram can be saved to PNG or JPG format |
| Modified through script and CSS | Modified through script only |
| Good text rendering capabilities | Poor text rendering capabilities |
| Give better performance with smaller number of objects or larger surface, or both | Give better performance with larger number of objects or smaller surface, or both |
| Better scalability. Can be printed with high quality at any resolution. Pixelation does not occur | Poor scalability. Not suitable for printing on higher resolution. Pixelation may occur |

* * *