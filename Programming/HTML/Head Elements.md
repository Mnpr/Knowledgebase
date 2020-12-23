Head Elements 

# Head

In this tutorial you will learn about the importance of head elements.

## The HTML head Element

The `<head>` element primarily is the container for all the head elements, which provide extra information about the document (metadata), or reference to other resources that are required for the document to display or behave correctly in a web browser.

The head elements collectively describes the properties of the document such as title, provide meta information like character set, instruct the browser where to find the style sheets or scripts that allows you to extend the HTML document in a highly active and interactive ways.

The HTML elements that can be used inside the [`<head>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-head-tag.php) element are: [`<title>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-title-tag.php), [`<base>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-base-tag.php), [`<link>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-link-tag.php), [`<style>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-style-tag.php), [`<meta>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-meta-tag.php), [`<script>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-script-tag.php) and the [`<noscript>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-noscript-tag.php) element.

## The HTML title Element

The `<title>` element defines the title of the document.

The title element is required in all HTML/XHTML documents to produce a valid document. Only one title element is permitted in a document and it must be placed within the `<head>` element. The title element contains plain text and entities; it may not contain other markup tags.

The title of the document may be used for different purposes. For example:

*   To display a title in the browser title bar and in the task bar.
*   To provide a title for the page when it is added to favorites or bookmarked.
*   To displays a title for the page in search-engine results.

The following example demonstrates how to place title in an HTML document.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <title>A simple HTML document</title>
</head>
<body>
    <p>Hello World!</p>
</body>
</html>
```

**Tip:** A good title should be short and specific to the document's content, because search engine's web crawlers pay particular attention to the words used in the title. The title should ideally be less than 65 characters in length. See the [guidelines for titles](https://www.tutorialrepublic.com/html-tutorial/../faq/what-is-the-maximum-length-of-title-and-meta-description-tag.php).

* * *

## The HTML base Element

The HTML `<base>` element is used to define a base URL for all relative links contained in the document, e.g. you can set the base URL once at the top of your page, and then all subsequent relative links will use that URL as a starting point. Here's an example:

#### Example


```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Defining a base URL</title>
    <base href="https://www.tutorialrepublic.com/">
</head>
<body>
    <p><a href="html-tutorial/html-head.php">HTML Head</a>.</p>
</body>
</html>
```

The hyperlink in the example above will actually resolve to `https://www.tutorialrepublic.com/html-tutorial/html-head.php` regardless of the URL of the current page. This is because the relative URL specified in the link: `html-tutorial/html-head.php` is added to the end of the base URL: `https://www.tutorialrepublic.com/`.

**Warning:** The HTML `<base>` element must appear before any element that refers to an external resource. HTML permits only one base element for each document.

* * *

## The HTML link Element

The `<link>` element defines the relationship between the current document and an external documents or resources. A common use of link element is to link to external style sheets.

#### Example

```markup
<head>
    <title>Linking Style Sheets</title>
    <link rel="stylesheet" href="style.css">
</head>
```

Please check out the [CSS tutorial](https://www.tutorialrepublic.com/css-tutorial/) section to learn about style sheets in detail.

**Note:** An HTML document's `<head>` element may contain any number of `<link>` elements. The `<link>` element has attributes, but no contents.

* * *

## The HTML style Element

The `<style>` element is used to define embedded style information for an HTML document. The style rules inside the `<style>` element specify how HTML elements render in a browser.

#### Example

```markup
<head>
    <title>Embedding Style Sheets</title>
    <style>
        body { background-color: YellowGreen; }
        h1 { color: red; }
        p { color: green; }
    </style>
</head>
```

**Note:** An embedded style sheet should be used when a single document has a unique style. If the same style sheet is used in multiple documents, then an external style sheet would be more appropriate. See the tutorial on [HTML styles](https://www.tutorialrepublic.com/html-tutorial/html-styles.php) to learn more about it.

* * *

## The HTML meta Element

The `<meta>` element provides metadata about the HTML document. Metadata is a set of data that describes and gives information about other data. Here's an example:

#### Example

```markup
<head>
    <title>Specifying Metadata</title>
    <meta charset="utf-8">
    <meta name="author" content="John Smith">
</head>
```

The meta element will be explained in more detail in the [next chapter](https://www.tutorialrepublic.com/html-tutorial/html-meta.php).

* * *

## The HTML script Element

The `<script>` element is used to define client-side script, such as JavaScript in HTML documents.

The following example will display a greeting message in the browser:

#### Example

```markup
<head>
    <title>Adding JavaScript</title>
    <script>
        document.write("<h1>Hello World!</h1>") 
    </script>
</head>
```

The script and noscript element will be explained in detail in the [later chapter](https://www.tutorialrepublic.com/html-tutorial/html-scripts.php).
