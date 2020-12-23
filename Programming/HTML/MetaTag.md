Meta Tag

# HTML Meta

In this tutorial you will learn how to use meta tags to provide metadata about a web page.

## Defining Metadata

The `<meta>` tags are typically used to provide structured metadata such as a document's _keywords_, _description_, _author name_, _character encoding_, and other metadata. Any number of meta tags can be placed inside the [head section](https://www.tutorialrepublic.com/html-tutorial/html-head.php) of an HTML or XHTML document.

Metadata will not be displayed on the web page, but will be machine parsable, and can be used by the browsers, search engines like Google or other web services.

The following section describes the use of meta tags for various purposes.

## Declaring Character Encoding in HTML

Meta tag typically used to declare character encoding inside HTML document.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Declaring Character Encoding</title> 
    <meta charset="utf-8">
</head>
<body>
    <h1>Hello World!</h1>
</body>
</html>
```

To set the character encoding inside a CSS document, the [`@charset`](https://www.tutorialrepublic.com/html-tutorial/../css-reference/css-charset-rule.php) at-rule is used.

**Note:** [UTF-8](https://en.wikipedia.org/wiki/UTF-8) is a very versatile and recommended character encoding to choose. However, if this is not specified, then the default encoding of the platform is used.

* * *

## Defining the Author of a Document

You can also use the meta tag to clearly define who is the author or creator of the web page.

The author can be an individual, the company as a whole or a third party.

#### Example

```markup
<head>
    <title>Defining Document's Author</title>
    <meta name="author" content="Alexander Howick">
</head>
```

**Note:** The `name` attribute of the meta tag defines the name of a piece of document-level metadata, while the `content` attribute gives the corresponding value. The `content` attribute value may contain text and entities, but it may not contain HTML tags.

* * *

## Keywords and Description for Search Engines

Some search engines use metadata especially keywords and descriptions to index web pages; however this may not necessarily be true. Keywords giving extra weight to a document's keywords and description provide a short synopsis of the page. Here's an example:

#### Example

```markup
<head>
    <title>Defining Keywords and Description</title>  
    <meta name="keywords" content="HTML, CSS, javaScript">
    <meta name="description" content="Easy to understand tutorials and references on HTML, CSS, javaScript and more..."> 
</head>
```

**Tip:** Search engines will often use the meta description of a page to create short synopsis for the page when it appear in search results. See the [guidelines for meta description](https://www.tutorialrepublic.com/html-tutorial/../faq/what-is-the-maximum-length-of-title-and-meta-description-tag.php).

* * *

## Configuring the Viewport for Mobile Devices

You can use the viewport meta tag to display the web pages correctly on mobile devices.

Without a viewport meta tag, mobile browsers render the web pages at typical desktop screen widths, and then scale it down to fit the mobile screen. As a result, it requires pinch-and-zoom to view the web page properly in mobile devices, which is very inconvenient.

The following demonstration shows two web pages — one _with viewport meta tag_ and other _without viewport meta tag_ set. Open these links on mobile devices to see how it works.

 [![Web Page with Viewport Meta Tag](../../../../_resources/be214ffff7524bde9c23359ae1a8c581.png) With Viewport Meta Tag](https://www.tutorialrepublic.com/examples/html/page-with-viewport-meta-tag.html)

[![Web Page without Viewport Meta Tag](../../../../_resources/3bec29d8cbb548bc8ef572d6d6176926.png)Without Viewport Meta Tag](https://www.tutorialrepublic.com/examples/html/page-without-viewport-meta-tag.html)

The viewport meta tag allows you to set the best viewport size and scaling limits for viewing the web pages on mobile devices. A typical viewport meta tag definition will look as follows:

#### Example

```markup
<head>
    <title>Configuring the Viewport</title> 
    <meta name="viewport" content="width=device-width, initial-scale=1">
</head>
```

The `width=device-width` key-value pair inside the `content` attribute sets the width of the viewport to same as the screen width of the device, whereas the `initial-scale=1` sets the initial scale or zoom level to 100% when the page is first loaded by the browser.

**Tip:** Always use the `<meta>` viewport tag in your web pages. It will make your website user-friendly and more accessible on mobile devices like cell phones and tablets.
* * *