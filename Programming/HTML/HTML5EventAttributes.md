HTML5 Event Attributes

# HTML5 Event Attributes

The HTML5 event attributes are global and can be applied to most of the elements.

## Event Attributes in HTML5

The following event attributes can be applied to the most of the elements for the execution of JavaScript when certain events occur, with some exceptions where it is not relevant such as elements found inside the `[<head>](https://www.tutorialrepublic.com/html-reference/html-head-tag.php)` section, e.g. `[<title>](https://www.tutorialrepublic.com/html-reference/html-title-tag.php)`, `[<base>](https://www.tutorialrepublic.com/html-reference/html-base-tag.php)`, `[<link>](https://www.tutorialrepublic.com/html-reference/html-link-tag.php)` etc.

## Window Events

Events related to the `window` object (applies to the `[<body>](https://www.tutorialrepublic.com/html-reference/html-body-tag.php)` tag):

| Attribute | Value | Description |
| --- | --- | --- |
| onafterprint | _script_ | Fires after the associated document is printed. |
| onbeforeprint | _script_ | Fires before the associated document is printed. |
| onbeforeunload | _script_ | Fires before a document being unloaded. |
| onerror | _script_ | Fires when document errors occur. |
| onhashchange | _script_ | Fires when the fragment identifier part of the document's URL i.e. the portion of a URL that follows the sign (#) changes. |
| onload | _script_ | Fires when the document has finished loading. |
| onmessage | _script_ | Fires when the message event occurs i.e. when user sends a cross-document message or a message is sent from a worker with `postMessage()` method. See [HTML5 Web Workers](https://www.tutorialrepublic.com/html-reference/../html-tutorial/html5-web-workers.php). |
| onoffline | _script_ | Fires when the network connection fails and the browser starts working offline. |
| ononline | _script_ | Fires when the network connections returns and the browser starts working online. |
| onpagehide | _script_ | Fires when the page is hidden, such as when a user is moving to another webpage. |
| onpageshow | _script_ | Fires when the page is shown, such as when a user navigates to a webpage. |
| onpopstate | _script_ | Fires when changes are made to the active history. |
| onresize | _script_ | Fires when the browser window is resized. |
| onstorage | _script_ | Fires when a [Web Storage](https://www.tutorialrepublic.com/html-reference/../html-tutorial/html5-web-storage.php) area is updated. |
| onunload | _script_ | Fires immediately before the document is unloaded or the browser window is closed. |

* * *

## Form Events

Events that occur due to the user interacting with the HTML form controls.

| Attribute | Value | Description |
| --- | --- | --- |
| onblur | _script_ | Fires when an element loses focus. |
| onchange | _script_ | Fires when the value or state of the element is changed. |
| onfocus | _script_ | Fires when the element receives focus. |
| oninput | _script_ | Fires when the value of an element is changed by the user. |
| oninvalid | _script_ | Fires when a submittable element do not satisfy their constraints during form validation. |
| onreset | _script_ | Fires when the user resets a form. |
| onselect | _script_ | Fires when some text is being selected or the current selection is changed by the user. |
| onsearch | _script_ | Fires when the user writes something in a [search input](https://www.tutorialrepublic.com/html-reference/../html-tutorial/html5-new-input-types.php#search-input) field. |
| onsubmit | _script_ | Fires when a form is submitted. |

* * *

## Mouse Events

Events that occur due to the user interacting with a pointing device such as a mouse:

| Attribute | Value | Description |
| --- | --- | --- |
| onclick | _script_ | Fires when the user clicks the left mouse button on the element. |
| ondblclick | _script_ | Fires when the user double-clicks on the element. |
| oncontextmenu | _script_ | Fires when a context menu is triggered by the user through right-click on the element. |
| ondrag | _script_ | Fires when the user drags an element. The `ondrag` event fires throughout the drag operation. |
| ondragend | _script_ | Fires when the user releases the mouse button at the end of a drag operation. |
| ondragenter | _script_ | Fires when the user drags an element to a valid drop target. |
| ondragleave | _script_ | Fires when an element leaves a valid drop target during a drag operation. |
| ondragover | _script_ | Fires when an element is being dragged over a valid drop target. |
| ondragstart | _script_ | Fires when the user starts to drag a text selection or selected element. |
| ondrop | _script_ | Fires when the mouse button is released during a drag-and-drop operation i.e. when dragged element is being dropped. |
| onmousedown | _script_ | Fires when the mouse button is pressed over an element. |
| onmousemove | _script_ | Fires when the user moves the mouse pointer over an element. |
| onmouseout | _script_ | Fires when the user moves the mouse pointer outside the boundaries of an element. |
| onmouseover | _script_ | Fires when the user moves the mouse pointer onto an element. |
| onmouseup | _script_ | Fires when the user releases the mouse button while the mouse is over an element. |
| onmousewheel | _script_ | [Deprecated](https://www.tutorialrepublic.com/html-reference/../definitions.php#deprecated) Use the `onwheel` attribute instead. |
| onscroll | _script_ | Fires when the user scrolls the contents of an element by scrolling the element's scrollbar. |
| onshow | _script_ | Fires when a `[contextmenu](#contextmenu)` event was fired onto an element that has a `contextmenu` attribute. |
| ontoggle | _script_ | Fires when the user opens or closes the `[<details>](https://www.tutorialrepublic.com/html-reference/html5-details-tag.php)` element. |
| onwheel | _script_ | Fires when the user scrolls the contents of an element by rolling the mouse wheel up or down over an element. |

* * *

## Keyboard Events

Events that occur by the user interaction with the keyboard:

| Attribute | Value | Description |
| --- | --- | --- |
| onkeydown | _script_ | Fires when the user presses a key. |
| onkeypress | _script_ | Fires when the user presses an alphanumeric key. |
| onkeyup | _script_ | Fires when the user releases a key. |

* * *

## Clipboard Events

Events related to modification of the clipboard, that is copy, cut and paste:

| Attribute | Value | Description |
| --- | --- | --- |
| oncopy | _script_ | Fires when the user copies the element or selection, adding it to the system clipboard. |
| oncut | _script_ | Fires when the element or selection is removed from the document and added to the system clipboard. |
| onpaste | _script_ | Fires when the user pastes data, transferring the data from the system clipboard to the document. |

* * *

## Media Events

Events that occur when handling media elements that are embedded inside the HTML documents, such as `[<audio>](https://www.tutorialrepublic.com/html-reference/html5-audio-tag.php)` and `[<video>](https://www.tutorialrepublic.com/html-reference/html5-video-tag.php)` elements:

| Attribute | Value | Description |
| --- | --- | --- |
| onabort | _script_ | Fires when playback is aborted, but not due to an error. |
| oncanplay | _script_ | Fires when enough data is available to play the media, at least for a couple of frames, but would require further buffering. |
| oncanplaythrough | _script_ | Fires when entire media can be played to the end without requiring to stop for further buffering. |
| oncuechange | _script_ | Fires when the text track cue in a `[<track>](https://www.tutorialrepublic.com/html-reference/html5-track-tag.php)` element changes. |
| ondurationchange | _script_ | Fires when the duration of the media changes. |
| onemptied | _script_ | Fires when the media element is reset to its initial state, either because of a fatal error during load, or because the `load()` method is called to reload it. |
| onended | _script_ | Fires when the end of playback is reached. |
| onerror | _script_ | Fires when an error occurs while fetching the media data. |
| onloadeddata | _script_ | Fires when media data is loaded at the current playback position. |
| onloadedmetadata | _script_ | Fires when metadata of the media (like duration and dimensions) has finished loading. |
| onloadstart | _script_ | Fires when loading of the media begins. |
| onpause | _script_ | Fires when playback is paused, either by the user or programmatically. |
| onplay | _script_ | Fires when playback of the media starts after having been paused i.e. when the `play()` method is requested. |
| onplaying | _script_ | Fires when the audio or video has started playing. |
| onprogress | _script_ | Fires periodically to indicate the progress while downloading the media data. |
| onratechange | _script_ | Fires when the playback rate or speed is increased or decreased, like slow motion or fast forward mode. |
| onseeked | _script_ | Fires when the seek operation ends. |
| onseeking | _script_ | Fires when the current playback position is moved. |
| onstalled | _script_ | Fires when the download has stopped unexpectedly. |
| onsuspend | _script_ | Fires when the loading of the media is intentionally stopped. |
| ontimeupdate | _script_ | Fires when the playback position changed, like when the user fast forwards to a different playback position. |
| onvolumechange | _script_ | Fires when the volume is changed, or playback is muted or unmuted. |
| onwaiting | _script_ | Fires when playback stops because the next frame of a video resource is not available. |

**Note:** The event attributes described above, however applied to all the HTML elements, though they are not useful for all elements. For example, only media elements will receive a volumechange event fired by the browser.
** *