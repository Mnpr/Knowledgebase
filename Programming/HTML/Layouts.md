Layouts

# HTML Layout

In this tutorial you will learn about the different methods of creating a web page layout.

## Creating Website Layouts

Creating a website layout is the activity of positioning the various elements that make a web page in a well-structured manner and give appealing look to the website.

You have seen most websites on the internet usually display their content in multiple rows and columns, formatted like a magazine or newspaper to provide the users a better reading and writing environment. This can be easily achieved by using the HTML tags, such as [`<table>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-table-tag.php), [`<div>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-div-tag.php), [`<header>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-header-tag.php), [`<footer>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-footer-tag.php), [`<section>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-section-tag.php), etc. and adding some [CSS styles](https://www.tutorialrepublic.com/html-tutorial/html-styles.php) to them.

## HTML Table Based Layout

Table provides the simplest way for creating layouts in HTML. Generally, this involves the process of putting the contents such as text, images, and so on into rows and columns.

The following layout is created using an HTML table with 3 rows and 2 columns — the first and last row spans both columns using the table's `colspan` attribute:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>HTML Table Layout</title>
</head>
<body style="margin:0px;">
    <table style="width:100%; border-collapse:collapse; font:14px Arial,sans-serif;">
        <tr>
            <td colspan="2" style="padding:10px 20px; background-color:#acb3b9;">
                <h1 style="font-size:24px;">Tutorial Republic</h1>
            </td>
        </tr>
        <tr style="height:170px;">
            <td style="width:20%; padding:20px; background-color:#d4d7dc; vertical-align: top;">
                <ul style="list-style:none; padding:0px; line-height:24px;">
                    <li><a href="#" style="color:#333;">Home</a></li>
                    <li><a href="#" style="color:#333;">About</a></li>
                    <li><a href="#" style="color:#333;">Contact</a></li>
                </ul>
            </td>
            <td style="padding:20px; background-color:#f2f2f2; vertical-align:top;">
                <h2>Welcome to our site</h2>
                <p>Here you will learn how to create websites...</p>
            </td>
        </tr>
        <tr>
            <td colspan="2" style="padding:5px; background-color:#acb3b9; text-align:center;">
                <p>copyright &copy; tutorialrepublic.com</p>
            </td>
        </tr>
    </table>
</body>
</html>
```

— The HTML code above will produce the following output:

**Warning:** The method used for creating layout in the above example is not wrong, but it's not recommended. Avoid [tables](https://www.tutorialrepublic.com/html-tutorial/html-tables.php) and [inline styles](https://www.tutorialrepublic.com/html-tutorial/html-styles.php#inline-styles) for creating layouts. Layouts created using tables often rendered very slowly. Tables should only be used to display tabular data.

* * *

## HTML Div Based Layout

Using the [`<div>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-div-tag.php) elements is the most common method of creating layouts in HTML. The `<div>` (stands for division) element is used for marking out a block of content, or set of other elements inside an HTML document. It can contain further other div elements if required.

The following example uses the div elements to create a multiple column layout. It will produce the same result as in the previous example that uses table element:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>HTML Div Layout</title>
<style>
    body {
        font: 14px Arial,sans-serif; 
        margin: 0px;
    }
    .header {
        padding: 10px 20px;
        background: #acb3b9; 
    }
    .header h1 {
        font-size: 24px;
    }
    .container {
        width: 100%;
        background: #f2f2f2; 
    }
    .nav, .section {
        float: left; 
        padding: 20px;
        min-height: 170px;
        box-sizing: border-box;
    }
    .nav {            
        width: 20%;             
        background: #d4d7dc;
    }
    .section {
        width: 80%;
    }
    .nav ul {
        list-style: none; 
        line-height: 24px;
        padding: 0px; 
    }
    .nav ul li a {
        color: #333;
    }    
    .clearfix:after {
        content: ".";
        display: block;
        height: 0;
        clear: both;
        visibility: hidden;
    }
    .footer {
        background: #acb3b9;            
        text-align: center;
        padding: 5px;
    }
</style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Tutorial Republic</h1>
        </div>
        <div class="wrapper clearfix">
            <div class="nav">
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </div>
            <div class="section">
                <h2>Welcome to our site</h2>
                <p>Here you will learn how to create websites...</p>
            </div>
        </div>
        <div class="footer">
            <p>copyright &copy; tutorialrepublic.com</p>
        </div>
    </div>
</body>
</html>
```

— The HTML code above will produce the same output as the previous example:

We've created this layout using the [CSS float](https://www.tutorialrepublic.com/css-tutorial/css-alignment.php#floating-elements) techniques, since most web browsers support it. Alternatively, you can also use the CSS3 flexbox to create modern and more flexible layouts. See the tutorial on [CSS3 flexible box layouts](https://www.tutorialrepublic.com/css-tutorial/css3-flexible-box-layouts.php) to learn about flexbox in detail.

**Tip:** Better web page layouts can be created by using the DIV elements and CSS. You can change the layout of all the pages of your website by editing just one CSS file. To learn about CSS in detail, please check out our [CSS tutorial](https://www.tutorialrepublic.com/css-tutorial/) section.

* * *

## Using the HTML5 Structural Elements

HTML5 has introduced the new structural elements such as [`<header>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-header-tag.php), [`<footer>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-footer-tag.php), [`<nav>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-nav-tag.php), [`<section>`](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-section-tag.php), etc. to define the different parts of a web page in a more semantic way.

You can consider these elements as a replacement for commonly used classes such as `.header`, `.footer`, `.nav`, `.section`, etc. The following example uses the new HTML5 structural elements to create the same layout that we have created in the previous examples.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>HTML5 Web Page Layout</title>
<style>
    body {
        font: 14px Arial,sans-serif; 
        margin: 0px;
    }
    header {
        padding: 10px 20px;
        background: #acb3b9; 
    }
    header h1 {
        font-size: 24px;
    }
    .container {
        width: 100%;
        background: #f2f2f2;  
    }
    nav, section {
        float: left; 
        padding: 20px;
        min-height: 170px;
        box-sizing: border-box;
    }
    section {
        width: 80%;
    }
    nav {
        width: 20%;             
        background: #d4d7dc;
    }    
    nav ul {
        list-style: none; 
        line-height: 24px;
        padding: 0px; 
    }
    nav ul li a {
        color: #333;
    }
    .clearfix:after {
        content: ".";
        display: block;
        height: 0;
        clear: both;
        visibility: hidden;
    }
    footer {
        background: #acb3b9;            
        text-align: center;
        padding: 5px;
    }
</style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Tutorial Republic</h1>
        </header>
        <div class="wrapper clearfix">
            <nav>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </nav>
            <section>
                <h2>Welcome to our site</h2>
                <p>Here you will learn how to create websites...</p>
            </section>
        </div>
        <footer>
            <p>copyright &copy; tutorialrepublic.com</p>
        </footer>
    </div>
</body>
</html>
```

— The HTML code above will also produce the same output as the previous example:

The following table provides a brief overview of new HTML5 structural elements.

| Tag | Description |
| --- | --- |
| `[<header>](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-header-tag.php)` | Represents the header of a document or a section. |
| `[<footer>](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-footer-tag.php)` | Represents the footer of a document or a section. |
| `[<nav>](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-nav-tag.php)` | Represents a section of navigation links. |
| `[<section>](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-section-tag.php)` | Represents a section of a document, such as header, footer etc. |
| `[<article>](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-article-tag.php)` | Represents an article, blog post, or other self-contained unit of information. |
| `[<aside>](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-aside-tag.php)` | Represents some content loosely related to the page content. |

Please check out the reference on [HTML5 tags](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html5-tags.php) to know about the newly introduced tags.
