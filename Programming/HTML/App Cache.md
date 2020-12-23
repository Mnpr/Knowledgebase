App Cache 

# HTML5 Application Cache

Typically most web-based applications will work only if you're online. But HTML5 introduces an application cache mechanism that allows the browser to automatically save the HTML file and all the other resources that needs to display it properly on the local machine, so that the browser can still access the web page and its resources without an internet connection.

Here are some advantages of using the HTML5 application cache feature:

*   **Offline browsing** — Users can use the application even when they're offline or there are unexpected disruptions in the network connection.
*   **Improve performance** — Cached resources load directly from the user's machine rather than the remote server hence web pages load faster and performing better.
*   **Reduce HTTP request and server load** — The browser will only have to download the updated/changed resources from the remote server that minimize the HTTP requests and saves precious bandwidth as well as reduce the load on the web server.

**Tip:** The HTML5's application cache feature is supported in all major modern web browsers like Firefox, Chrome, Opera, Safari and Internet Explorer 10 and above.

* * *

## Caching Files with a Manifest

To cache the files for offline uses, you need to complete the following steps:

### Step 1: Create a Cache Manifest File

A manifest is a special text file that tells the browsers what files to store, what files not to store, and what files to replace with something else. The manifest file always starts with the words `CACHE MANIFEST` (in uppercase). Here is an example of a simple manifest file:

#### Example

[Download](https://www.tutorialrepublic.com/html-tutorial/../examples/downloads/html5-cache-manifest-file.zip "Download Source Code")

```markup
CACHE MANIFEST
# v1.0 : 10-08-2014
 
CACHE:
# pages
index.html
 
# styles & scripts
css/theme.css
js/jquery.min.js
js/default.js
 
# images
/favicon.ico
images/logo.png
 
NETWORK:
login.php
 
FALLBACK:
/ /offline.html
```

## Explanation of code

You might think what that code was all about. OK, let's get straight into it. A manifest file can have three distinct sections: CACHE, NETWORK, and FALLBACK.

*   Files listed under the `CACHE:` section header (or immediately after the `CACHE MANIFEST` line) are explicitly cached after they're downloaded for the first time.
*   Files listed under the `NETWORK:` section header are white-listed resources that are never cached and aren't available offline. It means users can only access `login.php` page when they'r online.
*   The `FALLBACK:` section specifies fallback pages the browser should use in case the connection to the server cannot be established. Each entry in this section lists two URIs — first is the primary resource, the second is the fallback. For example, in our case `offline.html` page will be displayed if the user is offline. Also, both URIs must be from the same origin as the manifest file.
*   Lines starting with a hash symbol (`#`) are comment lines.

**Note:** If an application cache exists, the browser loads the document and its associated resources directly from the cache, without accessing the network. After that browser checks to see whether the manifest file has been updated on the server, and if it has been updated, the browser downloads the new version of the manifest and the resources listed in it.

**Warning:** Do not specify the manifest file itself in the cache manifest file, otherwise it will be nearly impossible to inform the browser a new manifest is available.

* * *

## Step 2: Using Your Cache Manifest File

After creating, upload your cache manifest file on the web server — make sure the web server is configured to serve the manifest files with the MIME type `text/cache-manifest`.

Now to put your cache manifest into effect, you need enable it in your web pages, by adding the manifest attribute to the root [`<html>`](https://www.tutorialrepublic.com/html-reference/html-html-tag.php) element, as shown below:

#### Example

Try this code »

```markup
<!DOCTYPE html>
<html lang="en" manifest="example.appcache">
<head>
    <title>Using the Application Cache</title>
</head>
<body>
    <!--The document content will be inserted here-->
</body>
</html>
```

**Note:** On the Apache web servers, the MIME type for the manifest (`.appcache`) files can be set by adding `AddType text/cache-manifest .appcache` to a `.htaccess` file within the root directory of the application, or the same directory as the application.

* * *