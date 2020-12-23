Introduction


# HTML
HTML is the main markup language for describing the structure of web pages. HTML stands for HyperText Markup Language. HTML is the basic building block of World Wide Web.

Hypertext is text displayed on a computer or other electronic device with references to other text that the user can immediately access, usually by a mouse click or key press.

Apart from text, hypertext may contain tables, lists, forms, images, and other presentational elements. It is an easy-to-use and flexible format to share information over the Internet.

Markup languages use sets of markup tags to characterize text elements within a document, which gives instructions to the web browsers on how the document should appear.

HTML was originally developed by Tim Berners-Lee in 1990. He is also known as the father of the web. In 1996, the World Wide Web Consortium (W3C) became the authority to maintain the HTML specifications. HTML also became an international standard (ISO) in 2000. HTML5 is the latest version of HTML. HTML5 provides a faster and more robust approach to web development.

**Tip:** Our HTML tutorial will help you to learn the fundamentals of the latest HTML5 language, from the basic to advanced topics step-by-step. If you're a beginner, start with the basic section and gradually move forward by learning a little bit every day.

* * *

## What You Can Do with HTML

There are lot more things you can do with HTML.

*   You can publish documents online with text, images, lists, tables, etc.
*   You can access web resources such as images, videos or other HTML document via hyperlinks.
*   You can create forms to collect user inputs like name, e-mail address, comments, etc.
*   You can include images, videos, sound clips, flash movies, applications and other HTML documents directly inside an HTML document.
*   You can create offline version of your website that work without internet.
*   You can store data in the user's web browser and access later on.
*   You can find the current location of your website's visitor.

The list does not end here, there are many other interesting things that you can do with HTML. You will learn about all of them in detail in upcoming chapters.

**Note:** HTML as described earlier is a markup language not a programming language, like Java, Ruby, PHP, etc. You need a web browser to view the HTML pages. The web browsers do not display the HTML tags, but uses the tags to interpret the content of the web pages.

* * *

## What This Tutorial Covers

This HTML tutorial series covers all the fundamentals of HTML, including the idea of elements and attributes, way of formatting the text using HTML tags, methods of adding the style information to the document, technique of inserting images and tables, process of creating lists and forms as well as method of including other HTML documents inside the current document, and so on.

Once you're familiar with the basics, you'll move on to next level that explains the concept of doctype, methods for creating the web page layouts, importance of adding meta information to the web pages, way of adding scripts, techniques of showing special characters, anatomy of a URL, and more.

Finally, you'll explore some advanced features introduced in HTML5 such as new input types, drawing graphics on the webpage, including audios and videos in the document, storing data on client-side using web storage, caching files, performing background work with web worker, as well as getting user's geographical coordinates, creating drag and drop application, and so on.

**Tip:** Every chapter in this tutorial contains lots of real-world examples that you can try and test using an online editor. These examples will help you to better understand the concept or topic. It also contains smart workarounds as well as useful tips and important notes.
***

## Getting Started

An HTML file is simply a text file saved with an .html or .htm extension.

## Creating Your First HTML Document

Let's walk through the following steps. At the end of this tutorial, you will have made an HTML file that displays "Hello world" message in your web browser.

### Step 1: Creating the HTML file

Open up your computer's plain text editor and create a new file.

**Tip:** We suggest you to use Notepad (on Windows), TextEdit (on Mac) or some other simple text editor to do this; don't use Word or WordPad! Once you understand the basic principles, you may switch to more advanced tools such as Adobe Dreamweaver.

### Step 2: Type some HTML code

Start with an empty window and type the following code:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <title>A simple HTML document</title>
</head>
<body>
    <p>Hello World!<p>
</body>
</html>
```

### Step 3: Saving the file

Now save the file on your desktop as "myfirstpage.html ".

**Note:** It is important that the extension `.html` is specified — some text editors, such as Notepad, will automatically save it as `.txt` otherwise.

To open the file in a browser. Navigate to your file then double click on it. It will open in your default Web browser. If it does not, open your browser and drag the file to it.

## Explanation of code

You might think what that code was all about. Well, let's find out.

*   The first line `<!DOCTYPE html>` is the [document type declaration](https://www.tutorialrepublic.com/html-tutorial/html-doctypes.php). It instructs the web browser that this document is an HTML5 document. It is case-insensitive.
*   The `<head>` element is a container for the tags that provides information about the document, for example, `<title>` tag defines the title of the document.
*   The `<body>` element contains the document's actual content (paragraphs, links, images, tables, and so on) that is rendered in the web browser and displayed to the user.

You will learn about the different HTML elements in detail in the upcoming chapters. For now, just focus on the basic structure of the HTML document.

**Note:** A DOCTYPE declaration appears at the top of a web page before all other elements; however the doctype declaration itself is not an HTML tag. Every HTML document requires a document type declaration to insure that your pages are displayed correctly.

**Tip:** The `<html>`, `<head>`, and `<body>` tags make up the basic skeleton of every web page. Content inside the `<head>` and `</head>` are invisible to users with one exception: the text between `<title>` and `</title>` tags which appears as the title on a browser tab.

* * *

## HTML Tags and Elements

HTML is written in the form of HTML elements consisting of markup tags. These markup tags are the fundamental characteristic of HTML. Every markup tag is composed of a keyword, surrounded by angle brackets, such as `<html>`, `<head>`, `<body>`, `<title>`, `<p>`, and so on.

HTML tags normally come in pairs like `<html>` and `</html>`. The first tag in a pair is often called the opening tag (or start tag), and the second tag is called the closing tag (or end tag).

An opening tag and a closing tag are identical, except a slash (`/`) after the opening angle bracket of the closing tag, to tell the browser that the command has been completed.

In between the start and end tags you can place appropriate contents. For example, a paragraph, which is represented by the `p` element, would be written as:

#### Example

```markup
<p>This is a paragraph.</p>
<!-- Paragraph with nested element -->
<p>
    This is <b>another</b> paragraph.
</p>
```

You will learn about the various [HTML elements](https://www.tutorialrepublic.com/html-tutorial/html-elements.php) in upcoming chapter.
***