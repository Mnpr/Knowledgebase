Doctype 

# HTML Doctypes

In this tutorial you will learn what the document type declaration is in HTML.

## Understanding the HTML5 Doctype

A Document Type Declaration, or DOCTYPE for short, is an instruction to the web browser about the version of markup language in which a web page is written.

A DOCTYPE declaration appears at the top of a web page before all other elements. According to the HTML specification or standards, every HTML document requires a valid document type declaration to insure that your web pages are displayed the way they are intended to be displayed.

The doctype declaration is usually the very first thing defined in an HTML document (even before the opening [`<html>`](https://www.tutorialrepublic.com/html-reference/html-html-tag.php) tag); however the doctype declaration itself is not an HTML tag.

The DOCTYPE for HTML5 is very short, concise, and case-insensitive.

&lt;!DOCTYPE html&gt;

Doctypes for earlier versions of HTML were longer because the HTML language was SGML-based and therefore required a reference to a DTD, but they are [obsolete](https://www.tutorialrepublic.com/html-tutorial/../definitions.php#obsolete) now.

With HTML5 this is no longer the case and the doctype declaration is only needed to enable the standard mode for documents written using the HTML syntax.

You can use the following markup as a template to create a new HTML5 document.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title><!-- Insert your title here --></title>
</head>
<body>
    <!-- Insert your content here -->
</body>
</html>
```

**Note:** The doctype declaration refers to a Document Type Definition (DTD). It is an instruction to the web browser about what version of the markup language the page is written in. The World Wide Web Consortium (W3C) provides DTDs for all HTML versions.

**Tip:** Must add a doctype declaration when creating an HTML document. Also, use the [W3C's Validator](http://validator.w3.org/) to check your HTML for markup or syntax error before publishing online.