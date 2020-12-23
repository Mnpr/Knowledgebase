HTML Images

# HTML Images

In this tutorial you will learn how to include images in an HTML document.

## Inserting Images into Web Pages

Images enhance visual appearance of the web pages by making them more interesting and colorful.

The `<img>` tag is used to insert images in the HTML documents. It is an empty element and contains attributes only. The syntax of the `<img>` tag can be given with:

<img src="_url_" alt="_some_text_">

The following example inserts three images on the web page:

#### Example

```markup
<img src="kites.jpg" alt="Flying Kites">
<img src="sky.jpg" alt="Cloudy Sky">
<img src="balloons.jpg" alt="Balloons">
```

Each image must carry at least two attributes: the `src` attribute, and an `alt` attribute.

The `src` attribute tells the browser where to find the image. Its value is the URL of the image file.

Whereas, the `alt` attribute provides an alternative text for the image, if it is unavailable or cannot be displayed for some reason. Its value should be a meaningful substitute for the image.

**Note:** Like `[<br>](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-br-tag.php)` , the `<img>` element is also an [empty element](https://www.tutorialrepublic.com/html-tutorial/html-elements.php#empty-elements), and does not have a closing tag. However, in XHTML it closes itself ending with "`/>`".

**Tip:** The required `alt` attribute provides alternative text description for an image if a user for some reason cannot able to view it because of slow connection, image is not available at the specified URL, or if the user uses a screen reader or non-graphical browser.

* * *

## Setting the Width and Height of an Image

The `width` and `height` attributes are used to specify the width and height of an image.

The values of these attributes are interpreted in pixels by default.

#### Example

```markup
<img src="kites.jpg" alt="Flying Kites" width="300" height="300">
<img src="sky.jpg" alt="Cloudy Sky" width="250" height="150">
<img src="balloons.jpg" alt="Balloons" width="200" height="200">
```

You can also use the `style` attribute to specify width and height for the images. It prevents style sheets from changing the image size accidently, since inline style has the highest priority.

#### Example

```markup
<img src="kites.jpg" alt="Flying Kites" style="width: 300px; height: 300px;">
<img src="sky.jpg" alt="Cloudy Sky" style="width: 250px; height: 150px;">
<img src="balloons.jpg" alt="Balloons" style="width: 200px; height: 200px;">
```

**Note:** It's a good practice to specify both the `width` and `height` attributes for an image, so that browser can allocate that much of space for the image before it is downloaded. Otherwise, image loading may cause distortion or flicker in your website layout.

* * *

## Using the HTML5 Picture Element

Sometimes, scaling an image up or down to fit different devices (or screen sizes) doesn't work as expected. Also, reducing the image dimension using the `width` and `height` attribute or property doesn't reduce the original file size. To address these problems HTML5 has introduced the `<picture>` tag that allows you to define multiple versions of an image to target different types of devices.

The `<picture>` element contains zero or more `<source>` elements, each referring to different image source, and one `<img>` element at the end. Also each `<source>` element has the `media` attribute which specifies a media condition (similar to the media query) that is used by the browser to determine when a particular source should be used. Let's try out an example:

#### Example

```markup
<picture>
    <source media="(min-width: 1000px)" srcset="logo-large.png">
    <source media="(max-width: 500px)" srcset="logo-small.png">
    <img src="logo-default.png" alt="My logo">
</picture>
```

**Note:** The browser will evaluate each child `<source>` element and choose the best match among them; if no matches are found, the URL of the `<img>` element's `src` attribute is used. Also, the `<img>` tag must be specified as the last child of the `<picture>` element.

* * *

## Working with Image Maps

An image map allows you to define hotspots on an image that acts just like a [hyperlink](https://www.tutorialrepublic.com/html-tutorial/html-links.php).

The basic idea behind creating image map is to provide an easy way of linking various parts of an image without dividing it into separate image files. For example, a map of the world may have each country hyperlinked to further information about that country.

Let's try out a simple example to understand how it actually works:

#### Example

```markup
<img src="objects.png" usemap="#objects" alt="Objects">
<map name="objects">
    <area shape="circle" coords="137,231,71" href="clock.html" alt="Clock">
    <area shape="poly" coords="363,146,273,302,452,300" href="sign.html" alt="Sign">
    <area shape="rect" coords="520,160,641,302" href="book.html" alt="Book">
</map>
```

The `name` attribute of the `<map>` tag is used to reference the map from the `<img>` tag using its `usemap` attribute. The `<area>` tag is used inside the `<map>` element to define the clickable areas on an image. You can define any number of clickable areas within an image.

**Note:** The image map should not be used for website navigation. They are not search engine friendly. A valid use of an image map is with a geographical map.

**Tip:** There are many online tools available for creating image maps. Some advanced editors like Adobe Dreamweaver also provides a set of tools for easily creating image maps.

* * *