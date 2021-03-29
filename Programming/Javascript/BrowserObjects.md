Browser Objects

# Browser Objects

## The Window Object

The `window` object represents a window containing a DOM document. A window can be the main window, a frame set or individual frame, or even a new window created with JavaScript.

If you remember from the preceding chapters we've used the `alert()` method in our scripts to show popup messages. This is a method of the `window` object.

In the next few chapters we will see a number of new methods and properties of the `window` object that enables us to do things such as prompt user for information, confirm user's action, open new windows, etc. which lets you to add more interactivity to your web pages.

* * *

## Calculating Width and Height of the Window

The `window` object provides the `innerWidth` and `innerHeight` property to find out the width and height of the browser window viewport (in pixels) including the horizontal and vertical scrollbar, if rendered. Here's is an example that displays the current size of the window on button click:

#### Example

```markup
<script>
function windowSize(){
    var w = window.innerWidth;
    var h = window.innerHeight;
    alert("Width: " + w + ", " + "Height: " + h);
}
</script>
 
<button type="button" onclick="windowSize();">Get Window Size</button>
```

However, if you want to find out the width and height of the window excluding the scrollbars you can use the `clientWidth` and `clientHeight` property of any DOM element (like a `div`), as follow:

#### Example

```markup
<script>
function windowSize(){
    var w = document.documentElement.clientWidth;
    var h = document.documentElement.clientHeight;
    alert("Width: " + w + ", " + "Height: " + h);
}
</script>
 
<button type="button" onclick="windowSize();">Get Window Size</button>
```

**Note:** The `document.documentElement` object represents the root element of the document, which is the [`<html>`](https://www.tutorialrepublic.com/javascript-tutorial/../html-reference/html-html-tag.php) element, whereas the `document.body` object represents the [`<body>`](https://www.tutorialrepublic.com/javascript-tutorial/../html-reference/html-body-tag.php) element. Both are supported in all major browsers.

* * *
* * *
## The Screen Object

The `window.screen` object contains information about the user's screen such as resolution (i.e. width and height of the screen), color depth, pixel depth, etc.

Since window object is at the top of the scope chain, so properties of the `window.screen` object can be accessed without specifying the `window.` prefix, for example `window.screen.width` can be written as `screen.width`. The following section will show you how to get information of the user's display using the screen object property of the window object.
* * *
## Getting Width and Height of the Screen

You can use the `screen.width` and `screen.height` property obtains the width and height of the user's screen in pixels. The following example will display your screen resolution on button click:

#### Example

```markup
<script>
function getResolution() {
    alert("Your screen is: " + screen.width + "x" + screen.height);
}
</script>
 
<button type="button" onclick="getResolution();">Get Resolution</button>
```

* * *

## Getting Available Width and Height of the Screen

The `screen.availWidth` and `screen.availHeight` property can be used to get the width and height available to the browser for its use on user's screen, in pixels.

The screen's available width and height is equal to screen's actual width and height minus width and height of interface features like the taskbar in Windows. Here's an example:

#### Example

```markup
<script>
function getAvailSize() {
    alert("Available Screen Width: " + screen.availWidth + ", Height: " + screen.availHeight);
}
</script>
 
<button type="button" onclick="getAvailSize();">Get Available Size</button>
```

* * *

## Getting Screen Color Depth

You can use the `screen.colorDepth` property to get the color depth of the user's screen. Color depth is the number of bits used to represent the color of a single pixel.

Color depth indicates how many colors a device screen is capable to produce. For example, screen with color depth of 8 can produce 256 colors (28).

Currently, most devices has screen with color depth of 24 or 32. In simple words more bits produce more color variations, like 24 bits can produce 224 = 16,777,216 color variations (_true colors_), whereas 32 bits can produce 232 = 4,294,967,296 color variations (_deep colors_).

#### Example

```markup
<script>
function getColorDepth() {
    alert("Your screen color depth is: " + screen.colorDepth);
}
</script>
 
<button type="button" onclick="getColorDepth();">Get Color Depth</button>
```

**Tip:** As of now virtually every computer and phone display uses 24-bit color depth. 24 bits almost always uses 8 bits of each of R, G, B. Whereas in case of 32-bit color depth, 24 bits are used for the color, and the remaining 8 bits are used for transparency.

* * *

## Getting Screen Pixel Depth

You can get the pixel depth of the screen using the `screen.pixelDepth` property. Pixel depth is the number of bits used per pixel by the system display hardware.

For modern devices, color depth and pixel depth are equal. Here's an example:

#### Example

```markup
<script>
function getPixelDepth() {
    alert("Your screen pixel depth is: " + screen.pixelDepth);
}
</script>
 
<button type="button" onclick="getPixelDepth();">Get Pixel Depth</button>
```
* * *
* * *


## The Location Object

The location property of a window (i.e. `window.location`) is a reference to a Location object; it represents the current URL of the document being displayed in that window.

Since window object is at the top of the scope chain, so properties of the `window.location` object can be accessed without `window.` prefix, for example `window.location.href` can be written as `location.href`. The following section will show you how to get the URL of page as well as hostname, protocol, etc. using the location object property of the window object.

## Getting the Current Page URL

You can use the `window.location.href` property to get the entire URL of the current page.

The following example will display the complete URL of the page on button click:

#### Example

```markup
<script>
function getURL() {
    alert("The URL of this page is: " + window.location.href);
}
</script>
 
<button type="button" onclick="getURL();">Get Page URL</button>
```

* * *

## Getting Different Part of a URL

Similarly, you can use other properties of the location object such as `protocol`, `hostname`, `port`, `pathname`, `search`, etc. to obtain different part of the URL.

Try out the following example to see how to use the location property of a window.

#### Example

```javascript
// Prints complete URL
document.write(window.location.href);
  
// Prints protocol like http: or https:
document.write(window.location.protocol); 
 
// Prints hostname with port like localhost or localhost:3000
document.write(window.location.host);
  
// Prints hostname like localhost or www.example.com
document.write(window.location.hostname);
 
// Prints port number like 3000
document.write(window.location.port);
  
// Prints pathname like /products/search.php
document.write(window.location.pathname); 
 
// Prints query string like ?q=ipad
document.write(window.location.search);
 
// Prints fragment identifier like #featured
document.write(window.location.hash);
```

**Note:** When you visit a website, you're always connecting to a specific port (e.g. http://localhost:3000). However, most browsers will simply not display the default port numbers, for example, 80 for HTTP and 443 for HTTPS.

* * *

## Loading New Documents

You can use the `assign()` method of the location object i.e. `window.location.assign()` to load another resource from a URL provided as parameter, for example:

#### Example

```markup
<script>
function loadHomePage() {
    window.location.assign("https://www.tutorialrepublic.com");
}
</script>
 
<button type="button" onclick="loadHomePage();">Load Home Page</button>
```

You can also use the `replace()` method to load new document which is almost the same as `assign()`. The difference is that it doesn't create an entry in the browser's history, meaning the user won't be able to use the back button to navigate to it. Here's an example:

#### Example

```markup
<script>
function loadHomePage(){
    window.location.replace("https://www.tutorialrepublic.com");
}
</script>
 
<button type="button" onclick="loadHomePage();">Load Home Page</button>
```

Alternatively, you can use the `window.location.href` property to load new document in the window. It produce the same effect as using `assign()` method. Here's is an example:

#### Example

```markup
<script>
function loadHomePage() {
    window.location.href = "https://www.tutorialrepublic.com";
}
</script>
 
<button type="button" onclick="loadHomePage();">Load Home Page</button>
```

* * *

## Reloading the Page Dynamically

The `reload()` method can be used to reload the current page dynamically.

You can optionally specify a Boolean parameter `true` or `false`. If the parameter is `true`, the method will force the browser to reload the page from the server. If it is `false` or not specified, the browser may reload the page from its cache. Here's an example:

#### Example

```markup
<script>
function forceReload() {
    window.location.reload(true);
}
</script>
 
<button type="button" onclick="forceReload();">Reload Page</button>
```

**Note:** The result of calling `reload()` method is different from clicking browser's Reload/Refresh button. The `reload()` method clears form control values that otherwise might be retained after clicking the Reload/Refresh button in some browsers.

* * *
* * *

## The History Object

The history property of the Window object refers to the History object. It contains the browser session history, a list of all the pages visited in the current frame or window.

Since Window is a global object and it is at the top of the scope chain, so properties of the Window object i.e. `window.history` can be accessed without `window.` prefix, for example `window.history.length` can be written as `history.length`.

The following section will show you how to get the information of user's browsing history. However, for security reasons scripts are not allowed to access the stored URLs.
* * *
## Getting the Number of Pages Visited

The `window.history.length` property can be used to get the number of pages in the session history of the browser for the current window. It also includes the currently loaded page.

You can use this property to find out how many pages a user has visited during the current browser session, as demonstrated in the following example:

#### Example

```markup
<script>
function getViews() {
    alert("You've accessed " + history.length + " web pages in this session.");
}
</script>
 
<button type="button" onclick="getViews();">Get Views Count</button>
```

* * *

## Going Back to the Previous Page

You can use the `back()` method of the History object i.e. `history.back()` to go back to the previous page in session history. It is same as clicking the browser's back button.

#### Example

```markup
<script>
function goBack() {
    window.history.back();
}
</script>
 
<button type="button" onclick="goBack();">Go Back</button>
```

If your browser back button is active then clicking this Go Back link takes you one step back.

* * *

## Going Forward to the Next Page

You can use the `forward()` method of the History object i.e. `history.forward()` to go forward to the next page in session history. It is same as clicking the browser's forward button.

#### Example

```markup
<script>
function goForward() {
    window.history.forward();
}
</script>
 
<button type="button" onclick="goForward();">Go Forward</button>
```

If your browser forward button is active then clicking this Go Forward link takes you one step forward.

* * *

## Going to a Specific Page

You can also load specific page from the session history using the `go()` method of the History object i.e. `history.go()`. This method takes an integer as a parameter. A negative integer moves backward in the history, and a positive integer moves forward in the history.

#### Example

```javascript
window.history.go(2);  // Go back two pages
window.history.go(-1); // Go back one page
window.history.go(0);  // Reload the current page
window.history.go(1);  // Go forward one page
window.history.go(2);  // Go forward two pages
```

**Tip:** If you attempt to access the page that does not exist in the window's history then the methods `back()`, `forward()` and `go()` will simply do nothing.

* * *
* * *

## The Navigator Object

The navigator property of a window (i.e. `window.navigator`) is a reference to a Navigator object; it is a read-only property which contains information about the user's browser.

Since Window is a global object and it is at the top of the scope chain, so properties of the Window object such as `window.navigator` can be accessed without `window.` prefix, for example `window.navigator.language` can be written as `navigator.language`.

The following section will show you how to get various information about user's browser.

## Detect Whether the Browser is Online or Offline

You can use the `navigator.onLine` property to detect whether the browser (or, application) is online or offline. This property returns a Boolean value `true` meaning online, or `false` meaning offline.

#### Example

```markup
<script>
function checkConnectionStatus() {
    if(navigator.onLine) {
        alert("Application is online.");
    } else {
        alert("Application is offline.");
    }
}
</script>
 
<button type="button" onclick="checkConnectionStatus();">Check Connection Status</button>
```

Browser fires online and offline events when a connection is establish or lost. You can attach handler functions to these events in order to customize your application for online and offline scenarios.

Let's take a look at the following JavaScript code to see how this works:

#### Example

```markup
<script>
function goOnline() {
    // Action to be performed when your application goes online
    alert("And we're back!");
}

function goOffline() {
    // Action to be performed when your application goes offline
    alert("Hey, it looks like you're offline.");
}

// Attaching event handler for the online event
window.addEventListener("online", goOnline);

// Attaching event handler for the offline event
window.addEventListener("offline", goOffline);
</script>

<p>Toggle your internet connection on/off to see how it works.</p>
```

The `goOffline()` function in the above example will be called automatically by the browser whenever the connection goes offline, whereas the `goOnline()` function will be called automatically by the browser when the connection status changes to online.

* * *

## Check Whether Cookies Are Enabled or Not

You can use the `navigator.cookieEnabled` to check whether [cookies](https://www.tutorialrepublic.com/javascript-tutorial/javascript-cookies.php) are enabled in the user's browser or not. This property returns a Boolean value `true` if cookies are enabled, or `false` if it isn't.

#### Example

```markup
<script>
function checkCookieEnabled() {
    if(navigator.cookieEnabled) {
        alert("Cookies are enabled in your browser.");
    } else {
        alert("Cookies are disabled in your browser.");
    }
}
</script>
 
<button type="button" onclick="checkCookieEnabled();">Check If Cookies are Enabled</button>
```

**Tip:** You should use the `navigator.cookieEnabled` property to determine whether the cookies are enabled or not before [creating or using cookies](https://www.tutorialrepublic.com/javascript-tutorial/javascript-cookies.php) in your JavaScript code.

* * *

## Detecting the Browser Language

You can use the `navigator.language` property to detect the language of the browser UI.

This property returns a string representing the language, e.g. "en", "en-US", etc.

#### Example

```markup
<script>
function checkLanguage() {
    alert("Your browser's UI language is: " + navigator.language);
}
</script>
 
<button type="button" onclick="checkLanguage();">Check Language</button>
```

* * *

## Getting Browser Name and Version Information

The Navigator object has five main properties that provide name and version information about the user's browser. The following list provides a brief overview of these properties:

*   `appName` — Returns the name of the browser. It always returns "Netscape", in any browser.
*   `appVersion` — Returns the version number and other information about the browser.
*   `appCodeName` — Returns the code name of the browser. It returns "Mozilla", for all browser.
*   `userAgent` — Returns the user agent string for the current browser. This property typically contains all the information in both `appName` and `appVersion`.
*   `platform` — Returns the platform on which browser is running (e.g. "Win32", "WebTV OS", etc.)

As you can see from the above descriptions, the value returned by these properties are misleading and unreliable, so don't use them to determine the user's browser type and version.

#### Example

```markup
<script>
function getBrowserInformation() {
	var info = "\n App Name: " + navigator.appName;
	   info += "\n App Version: " + navigator.appVersion;
	   info += "\n App Code Name: " + navigator.appCodeName;
	   info += "\n User Agent: " + navigator.userAgent;
	   info += "\n Platform: " + navigator.platform;

    alert("Here're the information related to your browser: " + info);
}
</script>
 
<button type="button" onclick="getBrowserInformation();">Get Browser Information</button>
```

* * *

## Check Whether the Browser is Java Enabled or Not

You can use the method `javaEnabled()` to check whether the current browser is Java-enabled or not.

This method simply indicates whether the preference that controls Java is on or off, it does not reveal whether the browser offers Java support or Java is installed on the user's system or not.

#### Example


```markup
<script>
function checkJavaEnabled() {
    if(navigator.javaEnabled()) {
        alert("Your browser is Java enabled.");
    } else {
        alert("Your browser is not Java enabled.");
    }
}
</script>
 
<button type="button" onclick="checkJavaEnabled();">Check If Java is Enabled</button>
```
* * *
