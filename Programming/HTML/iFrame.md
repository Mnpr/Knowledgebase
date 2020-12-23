HTML iFrame

# HTML iFrame

In this tutorial you will learn how to use an iframe to display a web page within another web page.

## What is iframe

An iframe or inline frame is used to display external objects including other web pages within a web page. An iframe pretty much acts like a mini web browser within a web browser. Also, the content inside an iframe exists entirely independent from the surrounding elements.

The basic syntax for adding an iframe to a web page can be given with:

`<iframe src="URL"></iframe>`

The URL specified in the `src` attribute points to the location of an external object or a web page.

The following example display "hello.html" file inside an iframe in current document.

#### Example


```markup
<iframe src="hello.html"></iframe>
```

* * *

## Setting Width and Height of an iFrame

The `height` and `width` attributes are used to specify the height and width of the iframe.

#### Example

```markup
<iframe src="hello.html" width="400" height="200"></iframe>
```

You can also use CSS to set the width and height of an iframe, as shown here:

#### Example

```markup
<iframe src="hello.html" style="width: 400px; height: 200px;"></iframe>
```

Please see the tutorial on [HTML styles](https://www.tutorialrepublic.com/html-tutorial/html-styles.php) to learn the methods of applying CSS to HTML elements.

**Note:** The `width` and `height` attribute values are specified in pixels by default, but you can also set these values in percentage, such as 50%, 100% and so on. The default width of an iframe is 300 pixels, whereas the default height is 150 pixels.

* * *

## Removing Default Frameborder

The iframe has a border around it by default. However, if you want to modify or remove the iframe borders, the best way is to use the CSS [`border`](https://www.tutorialrepublic.com/css-reference/css-border-property.php) property.

The following example will simply render the iframe without any borders.

#### Example

```markup
<iframe src="hello.html" style="border: none;"></iframe>
```

Similarly, you can use the `border` property to add the borders of your choice to an iframe. The following example will render the iframe with 2 pixels blue border.

#### Example

```markup
<iframe src="hello.html" style="border: 2px solid blue;"></iframe>
```

* * *

## Using an iFrame as Link Target

An iframe can also be used as a target for the [hyperlinks](https://www.tutorialrepublic.com/html-tutorial/html-links.php).

An iframe can be named using the `name` attribute. This implies that when a link with a `target` attribute with that name as value is clicked, the linked resource will open in that iframe.

Let's try out an example to understand how it basically works:

#### Example

```markup
<iframe src="demo-page.html" name="myFrame"></iframe>
<p><a href="https://www.tutorialrepublic.com" target="myFrame">Open TutorialRepublic.com</a></p>
```
* * *