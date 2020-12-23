Video

# HTML5 Video

## Embedding Video in HTML Document

Inserting video onto a web page was not relatively easy, because web browsers did not have a uniform standard for defining embedded media files like video.

In this chapter we'll demonstrates some of the many ways of adding videos on web pages, from the latest HTML5 `<video>` element to the popular YouTube videos.

## Using the HTML5 video Element

The newly introduced HTML5 `<video>` element provides a standard way to embed video in web pages. However, the video element is relatively new, but it works in most of the modern web browsers.

The following example simply inserts a video into the HTML document, using the browser default set of controls, with one source defined by the `src` attribute.

#### Example

```markup
<video controls="controls" src="media/shuttle.mp4">
    Your browser does not support the HTML5 Video element.
</video>
```

A video, using the browser default set of controls, with alternative sources.

#### Example

```markup
<video controls="controls">
    <source src="media/shuttle.mp4" type="video/mp4">
    <source src="media/shuttle.ogv" type="video/ogg">
    Your browser does not support the HTML5 Video element.
</video>
```

* * *

## Using the object Element

The `<object>` element is used to embed different kinds of media files into an HTML document. Initially, this element was used to insert ActiveX controls, but according to the specification, an object can be any media object such as video, audio, PDF files, Flash animations or even images.

The following code fragment embeds a Flash video into a web page.

#### Example

```markup
<object data="media/blur.swf" width="400px" height="200px"></object>
```

Only browsers or applications that support Flash will play this video.

**Warning:** The `[<object>](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-object-tag.php)` element is not supported widely and very much depends on the type of the object that's being embedded. Other methods could be a better choice in many cases. iPad and iPhone device cannot display Flash videos.

* * *

## Using the embed Element

The `<embed>` element is used to embed multimedia content into an HTML document.

The following code fragment embeds a Flash video into a web page.

#### Example

```markup
<embed src="media/blur.swf" width="400px" height="200px">
```

**Warning:** However, the `<embed>` element is very well supported in current web browsers and it is also defined as standard in HTML5, but your video might not played due to lack of browser support for Flash or unavailability of plugins.

* * *

## Embedding the YouTube Videos

This is the easiest and popular way to embed videos files in the web pages. Just upload the video on YouTube and insert HTML code to display that video in your web page.

Here's a live example followed by the explanation of whole process:

### Step 1: Upload video

Go to YouTube upload video page and follow the instructions to upload your video.

### Step 2: Creating the HTML Code to embed the video

When you open your uploaded video in YouTube you will see something like the following figure at the bottom of the video. Browse and open your uploaded video in YouTube. Now look for the share button which is located just below the video as shown in the figure.

![Share YouTube Videos](../../../../_resources/870aef5a9f1f4b939d49459ca8884696.png)

When you click the share button, a share panel will open displaying some more buttons. Now click on the Embed button, it will generate the HTML code to directly embed the video into the web pages. Just copy and paste that code into your HTML document where you want to display the video and you're all set. By default video embedded inside an iframe.

![Share YouTube Videos](../../../../_resources/a86920f604bf4dbeb29662ddca09e1e0.png)

You can further customize this embed code such as changing the video size by selecting the customization option given just below the embed-code input box.

The following example simply embeds a video from the YouTube. Let's try it out:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>YouTube Video</title>
</head>
<body>
    <iframe width="560" height="315" src="//www.youtube.com/embed/YE7VzlLtp-4" frameborder="0" allowfullscreen></iframe>
</body>
</html>
```
* * *