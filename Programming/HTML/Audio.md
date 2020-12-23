 Audio

# HTML5 Audio

## Embedding Audio in HTML Document

Inserting audio onto a web page was not easy before, because web browsers did not have a uniform standard for defining embedded media files like audio.

In this chapter we'll demonstrates some of the many ways to embed sound in your webpage, from the use of a simple link to the use of the latest HTML5 `<audio>` element.

* * *

## Using the HTML5 audio Element

The newly introduced HTML5 `<audio>` element provides a standard way to embed audio in web pages. However, the audio element is relatively new but it works in most of the modern web browsers.

The following example simply inserts an audio into the HTML5 document, using the browser default set of controls, with one source defined by the `src` attribute.

#### Example

```markup
<audio controls="controls" src="media/birds.mp3">
    Your browser does not support the HTML5 Audio element.
</audio>
```

An audio, using the browser default set of controls, with alternative sources.

#### Example

```markup
<audio controls="controls">
    <source src="media/birds.mp3" type="audio/mpeg">
    <source src="media/birds.ogg" type="audio/ogg">
    Your browser does not support the HTML5 Audio element.
</audio>
```

The 'ogg' track in the above example works in Firefox, Opera and Chrome, while the same track in the 'mp3' format is added to make the audio work in Internet Explorer and Safari.

* * *

## Linking Audio Files

You can make links to your audio files and play it by ticking on them.

Let's try out the following example to understand how this basically works:

#### Example

```markup
<a href="media/sea.mp3">Track 1</a>
<a href="media/wind.mp3">Track 2</a>
```

* * *

## Using the object Element

The `<object>` element is used to embed different kinds of media files into an HTML document. Initially, this element was used to insert ActiveX controls, but according to the specification, an object can be any media object such as audio, video, PDF files, Flash animations or even images.

The following example code embeds a simple audio file into a web page.

#### Example

```markup
<object data="media/sea.mp3"></object>
<object data="media/sea.ogg"></object>
```

**Warning:** The `[<object>](https://www.tutorialrepublic.com/html-tutorial/../html-reference/html-object-tag.php)` element is not supported widely and very much depends on the type of the object that's being embedded. Other methods like HTML5 `<audio>` element or third-party HTML5 audio players could be a better choice in many cases.

* * *

## Using the embed Element

The `<embed>` element is used to embed multimedia content into an HTML document.

The following code fragment embeds audio files into a web page.

#### Example

```markup
<embed src="media/wind.mp3">
<embed src="media/wind.ogg">
```

**Warning:** However the `<embed>` element is very well supported in current browsers and defined as standard in HTML5, but your audio might not played due to lack of browser support for that file format or unavailability of plugins.

* * *