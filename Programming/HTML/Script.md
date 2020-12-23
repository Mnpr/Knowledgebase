 HTML Script

# HTML Script

In this tutorial you will learn how to include JavaScript in an HTML document.

## Working with Client-side Script

Client-side scripting refers to the type of computer programs that are executed by the user's web browser. JavaScript (JS) is the most popular client-side scripting language on the web.

The `<script>` element is used to embed or reference JavaScript within an HTML document to add interactivity to web pages and provide a significantly better user experience.

Some of the most common uses of JavaScript are form validation, generating alert messages, creating image gallery, show hide content, DOM manipulation, and many more.

## Adding JavaScript to HTML Pages

JavaScript can either be embedded directly inside the HTML page or placed in an external script file and referenced inside the HTML page. Both methods use the `<script>` element.

## Embedding JavaScript

To embed JavaScript in an HTML file, just add the code as the content of a `<script>` element.

The JavaScript in the following example write a string of text to a web page.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Embedding JavaScript</title>
</head>
<body>
    <div id="greet"></div>
    <script>
        document.getElementById("greet").innerHTML = "Hello World!";
    </script>
</body>
</html>
```

**Tip:** Ideally, script elements should be placed at the bottom of the page, before the closing body tag i.e. `</body>`, because when browser encounters a script it pauses rendering the rest of the page until it parses the script that may significantly impact your site performance.

* * *

## Calling External JavaScript File

You can also place your JavaScript code into a separate file (with a `.js` extension), and call that file in your HTML document through the `src` attribute of the `<script>` tag.

This is useful if you want the same script available to multiple documents. It saves you from repeating the same task over and over again and makes your website much easier to maintain.

The following example demonstrates how to link external JS file in HTML.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Linking External JavaScript</title>
</head>
<body>
    <div id="greet"></div>
    <script src="hello.js"></script>
</body>
</html>
```

**Note:** When the `src` attribute is specified, the `<script>` element must be empty. This simply means that you cannot use the same `<script>` element to both embed the JavaScript and to link to an external JavaScript file in an HTML document.

**Tip:** JavaScript files are normal text files with `.js` extension, such as "hello.js". Also, the external JavaScript file contains only JavaScript statements; it does not contain the `<script>...</script>` element like embedded JavaScript.

* * *

## The HTML noscript Element

The `<noscript>` element is used to provide an alternate content for users that have either disabled JavaScript in their browser or have a browser that doesn't support client-side scripting.

This element can contain any HTML elements, aside from `<script>`, that can be included in the [`<body>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-body-tag.php) element of a normal HTML page. Let's check out an example:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Noscript Demo</title>        
</head>
<body>
    <div id="greet"></div>
    <script>
        document.getElementById("greet").innerHTML = "Hello World!";
    </script>
    <noscript>
        <p>Oops! This website requires a JavaScript-enabled browser.</p>
    </noscript>
</body>
</html>
```

**Note:** The content inside the `noscript` element will only be displayed if the user's browser doesn't support scripting, or scripting is disabled in the browser.
* * *