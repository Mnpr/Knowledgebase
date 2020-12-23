Attributes

# HTML Attributes

In this tutorial you will learn how to use attributes to give more meaning to HTML tags.

## What are Attributes

Attributes define additional characteristics or properties of the element such as width and height of an image. Attributes are always specified in the start tag (or opening tag) and usually consists of name/value pairs like `name="value"`. Attribute values should always be enclosed in quotation marks.

Also, some attributes are required for certain elements. For instance, an `<img>` tag must contain a `src` and `alt` attributes. Let's take a look at some examples of the attributes usages:

#### Example

[Try this code »](https://www.tutorialrepublic.com/html-tutorial/../codelab.php?topic=html&file=attributes "Try this code using online Editor")

```markup
<img src="images/smiley.png" width="30" height="30" alt="Smiley">
<a href="https://www.google.com/" title="Search Engine">Google</a>
<abbr title="Hyper Text Markup Language">HTML</abbr>
<input type="text" value="John Doe">
```

In the above example `src` inside the `<img>` tag is an attribute and image path provided is its value. Similarly `href` inside the `<a>` tag is an attribute and the link provided is its value, and so on.

**Tip:** Both single and double quotes can be used to quote attribute values. However, double quotes are most common. In situations where the attribute value itself contains double quotes it is necessary to wrap the value in single quotes, e.g., `value='John "Williams" Jr.'`

There are several attributes in HTML5 that do not consist of name/value pairs but consists of just name. Such attributes are called Boolean attributes. Examples of some commonly used Boolean attributes are `checked`, `disabled`, `readonly`, `required`, etc.

#### Example

```markup
<input type="email" required>
<input type="submit" value="Submit" disabled>
<input type="checkbox" checked>
<input type="text" value="Read only text" readonly>
```

You will learn about all these elements in detail in upcoming chapters.

**Note:** Attribute values are generally case-insensitive, except certain attribute values, like the `id` and `class` attributes. However, World Wide Web Consortium (W3C) recommends lowercase for attributes values in their specification.

* * *

## General Purpose Attributes

There are some attributes, such as `id`, `title`, `class`, `style`, etc. that you can use on the majority of HTML elements. The following section describes their usages.

### The id Attribute

The `id` attribute is used to give a unique name or identifier to an element within a document. This makes it easier to select the element using CSS or JavaScript.

#### Example

```markup
<input type="text" id="firstName">
<div id="container">Some content</div>
<p id="infoText">This is a paragraph.</p>
```

**Note:** The `id` of an element must be unique within a single document. No two elements in the same document can be named with the same `id`, and each element can have only one `id`.

### The class Attribute

Like `id` attribute, the `class` attribute is also used to identify elements. But unlike `id`, the `class` attribute does not have to be unique in the document. This means you can apply the same class to multiple elements in a document, as shown in the following example:

#### Example

```markup
<input type="text" class="highlight">
<div class="box highlight">Some content</div>
<p class="highlight">This is a paragraph.</p>
```

**Tip:** Since a `class` can be applied to multiple elements, therefore any style rules that are written to that `class` will be applied to all the elements having that `class`.

### The title Attribute

The `title` attribute to is used to provide advisory text about an element or its content. Try out the following example to understand how this actually works.

#### Example

```markup
<abbr title="World Wide Web Consortium">W3C</abbr>
<a href="images/kites.jpg" title="Click to view a larger image">
    <img src="images/kites-thumb.jpg" alt="kites">
</a>
```

**Tip:** The value of the `title` attribute (i.e. title text) is displayed as a tooltip by the web browsers when the user place mouse cursor over the element.

### The style Attribute

The `style` attribute allows you to specify CSS styling rules such as color, font, border, etc. directly within the element. Let's check out an example to see how it works:

#### Example

```markup
<p style="color: blue;">This is a paragraph.</p>
<img src="images/sky.jpg" style="width: 300px;" alt="Cloudy Sky">
<div style="border: 1px solid red;">Some content</div>
```

You will learn more about styling HTML elements in [HTML styles](https://www.tutorialrepublic.com/html-tutorial/html-styles.php) chapter.

The attributes we've discussed above are also called global attributes. For more global attributes please check out the [HTML5 global attributes reference](https://www.tutorialrepublic.com/html-reference/html5-global-attributes.php).

A complete list of attributes for each HTML element is listed inside [HTML5 tag reference](https://www.tutorialrepublic.com/html-reference/html-tag-list.php).
* * *