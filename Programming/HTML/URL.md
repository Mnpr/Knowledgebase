URL

# HTML URL

In this tutorial you will learn about the different parts of a URL in detail.

## What is URL?

URL stands for **U**niform **R**esource **L**ocator is the global address of documents and other resources on the World Wide Web. Its main purpose is to identify the location of a document and other resources available on the internet, and specify the mechanism for accessing it through a web browser.

For instance, if you look at the address bar of your browser you will see:

https://www.tutorialrepublic.com/html-tutorial/html-url.php

— This is the URL of the web page you are viewing right now.

* * *

## The URL Syntax

The general syntax of URLs is the following:

scheme://host:port/path?query-string#fragment-id

A URL has a linear structure and normally consists of some of the following:

*   **Scheme name** — The scheme identifies the protocol to be used to access the resource on the Internet. The scheme names followed by the three characters `://` (a colon and two slashes). The most commonly used protocols are `http://`, `https://`, `ftp://`, and `mailto://`.
*   **Host name** — The host name identifies the host where resource is located. A hostname is a domain name assigned to a host computer. This is usually a combination of the host's local name with its parent domain's name. For example, `www.tutorialrepublic.com` consists of host's machine name `www` and the domain name `tutorialrepublic.com`.
*   **Port Number** — Servers often deliver more than one type of service, so you must also tell the server what service is being requested. These requests are made by port number. Well-known port numbers for a service are normally omitted from the URL. For example, web service HTTP runs by default over port 80, HTTPS runs by default over port 443.
*   **Path** — The path identifies the specific resource within the host that the user wants to access. For example, `/html/html-url.php`, `/news/technology/`, etc.
*   **Query String** — The query string contains data to be passed to server-side scripts, running on the web server. For example, parameters for a search. The query string preceded by a question mark (`?`), is usually a string of name and value pairs separated by ampersand (`&`), for example, `?first_name=John&last_name=Corner`, `q=mobile+phone`, and so on.
*   **Fragment identifier** — The fragment identifier, if present, specifies a location within the page. Browser may scroll to display that part of the page. The fragment identifier introduced by a hash character (`#`) is the optional last part of a URL for a document.

**Note:** Scheme and host components of a URL are not case-sensitive, but path and query string are case-sensitive. Usually the whole URL is specified in lower case.

* * *
# HTML URL Encoding

In this tutorial you will learn how to encode URL to safely transmit data over the internet.

## What is URL Encoding

According to [RFC 3986](https://tools.ietf.org/html/rfc3986), the characters in a URL only limited to a defined set of reserved and unreserved US-ASCII characters. Any other characters are not allowed in a URL. But URL often contains characters outside the US-ASCII character set, so they must be converted to a valid US-ASCII format for worldwide interoperability. URL-encoding, also known as percent-encoding is a process of encoding URL information so that it can be safely transmitted over the internet.

To map the wide range of characters that is used worldwide, a two-step process is used:

*   At first the data is encoded according to the UTF-8 character encoding.
*   Then only those bytes that do not correspond to characters in the unreserved set should be percent-encoded like %HH, where HH is the hexadecimal value of the byte.

For example, the string: **François** would be encoded as: **Fran%C3%A7ois**

Ç, ç (c-cedilla) is a Latin script letter.

* * *

## Reserved Characters

Certain characters are reserved or restricted from use in a URL because they may (or may not) be defined as delimiters by the generic syntax in a particular [URL scheme](https://www.tutorialrepublic.com/html-tutorial/html-url.php). For example, forward slash `/` characters are used to separate different parts of a URL.

If data for a URL component contains character that would conflict with a reserved set of characters, which is defined as a delimiter in the URL scheme then the conflicting character must be percent-encoded before the URL is formed. Reserved characters in a URL are:

|     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `!` | `#` | `$` | `&` | `'` | `(` | `)` | `*` | `+` | `,` | `/` | `:` | `;` | `=` | `?` | `@` | `[` | `]` |
| `%21` | `%23` | `%24` | `%26` | `%27` | `%28` | `%29` | `%2A` | `%2B` | `%2C` | `%2F` | `%3A` | `%3B` | `%3D` | `%3F` | `%40` | `%5B` | `%5D` |

* * *

## Unreserved Characters

Characters that are allowed in a URL but do not have a reserved purpose are called unreserved. These include uppercase and lowercase letters, decimal digits, hyphen, period, underscore, and tilde. The following table lists all the unreserved characters in a URL:

|     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `A` | `B` | `C` | `D` | `E` | `F` | `G` | `H` | `I` | `J` | `K` | `L` | `M` | `N` | `O` | `P` | `Q` | `R` | `S` | `T` | `U` | `V` | `W` | `X` | `Y` | `Z` |
| `a` | `b` | `c` | `d` | `e` | `f` | `g` | `h` | `i` | `j` | `k` | `l` | `m` | `n` | `o` | `p` | `q` | `r` | `s` | `t` | `u` | `v` | `w` | `x` | `y` | `z` |
| `0` | `1` | `2` | `3` | `4` | `5` | `6` | `7` | `8` | `9` | `-` | `_` | `.` | `~` |     |     |     |     |     |     |     |     |     |     |     |     |

* * *

## URL Encoding Converter

The following converter encodes and decodes the characters according to [RFC 3986](https://tools.ietf.org/html/rfc3986).

François

Enter some character and click on encode or decode button to see the output.

* * *