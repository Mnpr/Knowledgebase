Regular Expressions

# JavaScript Regular Expressions
 Pattern matching in an efficient way in JavaScript.
* * *


## What is Regular Expression

Regular Expressions, commonly known as "**regex**" or "**RegExp**", are a specially formatted text strings used to find patterns in text. Regular expressions are one of the most powerful tools available today for effective and efficient text processing and manipulations. For example, it can be used to verify whether the format of data i.e. name, email, phone number, etc. entered by the user is correct or not, find or replace matching string within text content, and so on.

JavaScript supports Perl style regular expressions. Why Perl style regular expressions? Because Perl (_Practical Extraction and Report Language_) was the first mainstream programming language that provided integrated support for regular expressions and it is well known for its strong support of regular expressions and its extraordinary text processing and manipulation capabilities.

Let's begin with a brief overview of the commonly used JavaScript's built-in methods for performing pattern-matching before delving deep into the world of regular expressions.

| Function | What it Does |
| --- | --- |
| `exec()` | Search for a match in a string. It returns an array of information or `null` on mismatch. |
| `test()` | Test whether a string matches a pattern. It returns `true` or `false`. |
| `search()` | Search for a match within a string. It returns the index of the first match, or `-1` if not found. |
| `replace()` | Search for a match in a string, and replaces the matched substring with a replacement string. |
| `match()` | Search for a match in a string. It returns an array of information or `null` on mismatch. |
| `split()` | Splits up a string into an array of substrings using a regular expression. |

**Note:** The methods `exec()` and `test()` are RegExp methods that takes a string as a parameter, whereas the methods `search()`, `replace()`, `match()` and `split()` are String methods that takes a regular expression as a parameter.

* * *

## Defining Regular Expressions

In JavaScript, regular expressions are represented by RegExp object, which is a native JavaScript object like String, Array, and so on. There are two ways of creating a new RegExp object — one is using the literal syntax, and the other is using the `RegExp()` constructor.

The literal syntax uses forward slashes (`_/pattern/_`) to wrap the regular expression pattern, whereas the constructor syntax uses quotes (`_"pattern"_`). The following example demonstrates both ways of creating a regular expression that matches any string that begins with "Mr.".

#### Example

```javascript
// Literal syntax 
var regex = /^Mr\./;

// Constructor syntax
var regex = new RegExp("^Mr\\.");
```

As you can see, the regular expression literal syntax is shorter and easier to read. Therefore it is preferable to use the literal syntax. We'll also use it throughout this tutorial.

**Note:** When using the constructor syntax, you've to double-escape [special characters](#special-characters), which means to match "." you need to write `"\\."` instead of `"\."`. If there is only one backslash, it would be interpreted by JavaScript's string parser as an escaping character and removed.

## Pattern Matching with Regular Expression

Regular expression patterns include the use of letters, digits, punctuation marks, etc., plus a set of special regular expression characters (do not confuse with the [HTML special characters](https://www.tutorialrepublic.com/javascript-tutorial/../html-tutorial/html-entities.php)).

The characters that are given special meaning within a regular expression, are:  
`.` `*` `?` `+` `[` `]` `(` `)` `{` `}` `^` `$` `|` `\`. You will need to backslash these characters whenever you want to use them literally. For example, if you want to match ".", you'd have to write `\.`. All other characters automatically assume their literal meanings.

The following sections describe the various options available for formulating patterns:

## Character Classes

Square brackets surrounding a pattern of characters are called a character class e.g. `[abc]`. A character class always matches a single character out of a list of specified characters that means the expression `[abc]` matches only a, b or c character.

Negated character classes can also be defined that match any character except those contained within the brackets. A negated character class is defined by placing a caret (`^`) symbol immediately after the opening bracket, like `[^abc]`, which matches any character except a, b, and c.

You can also define a range of characters by using the hyphen (`-`) character inside a character class, like `[0-9]`. Let's look at some examples of the character classes:

| RegExp | What it Does |
| --- | --- |
| `[abc]` | Matches any one of the characters a, b, or c. |
| `[^abc]` | Matches any one character other than a, b, or c. |
| `[a-z]` | Matches any one character from lowercase a to lowercase z. |
| `[A-Z]` | Matches any one character from uppercase a to uppercase z. |
| `[a-Z]` | Matches any one character from lowercase a to uppercase Z. |
| `[0-9]` | Matches a single digit between 0 and 9. |
| `[a-z0-9]` | Matches a single character between a and z or between 0 and 9. |

The following example will show you how to find whether a pattern exists within a string or not using the regular expression with the JavaScript `test()` method:

#### Example

```javascript
var regex = /ca[kf]e/;
var str = "He was eating cake in the cafe.";

// Test the string against the regular expression
if(regex.test(str)) {
    alert("Match found!");
} else {
    alert("Match not found.");
}
```

Further, you can add the [global flag](#flags) `g` to a regular expression to find all matches in a string:

#### Example

```javascript
var regex = /ca[kf]e/g;
var str = "He was eating cake in the cafe.";
var matches = str.match(regex);
alert(matches.length); // Outputs: 2
```

**Tip:** Regular expressions aren't exclusive to JavaScript. Languages such as Java, Perl, Python, PHP, etc. use the same notation for finding patterns in text.

* * *

## Predefined Character Classes

Some character classes such as digits, letters, and whitespaces are used so frequently that there are shortcut names for them. The following table lists those predefined character classes:

| Shortcut | What it Does |
| --- | --- |
| `.` | Matches any single character except newline `\n`. |
| `\d` | matches any digit character. Same as `[0-9]` |
| `\D` | Matches any non-digit character. Same as `[^0-9]` |
| `\s` | Matches any whitespace character (space, tab, newline or carriage return character).  <br>Same as `[ \t\n\r]` |
| `\S` | Matches any non-whitespace character.  <br>Same as `[^ \t\n\r]` |
| `\w` | Matches any word character (definned as a to z, A to Z,0 to 9, and the underscore).  <br>Same as `[a-zA-Z_0-9]` |
| `\W` | Matches any non-word character. Same as `[^a-zA-Z_0-9]` |

The following example will show you how to find and replace space with a hyphen character in a string using regular expression with the JavaScript `replace()` method:

#### Example

```javascript
var regex = /\s/g;
var replacement = "-";
var str = "Earth revolves around\nthe\tSun";

// Replace spaces, newlines and tabs
document.write(str.replace(regex, replacement) + "<hr>");

// Replace only spaces
document.write(str.replace(/ /g, "-"));
```

* * *

## Repetition Quantifiers

In the previous section we've learnt how to match a single character in a variety of fashions. But what if you want to match on more than one character? For example, let's say you want to find out words containing one or more instances of the letter p, or words containing at least two p's, and so on.

This is where quantifiers come into play. With quantifiers you can specify how many times a character in a regular expression should match. Quantifiers can be applied to the individual characters, as well as [classes of characters](#character-classes), and [groups of characters](#grouping) contained by the parentheses.

The following table lists the various ways to quantify a particular pattern:

| RegExp | What it Does |
| --- | --- |
| `p+` | Matches one or more occurrences of the letter p. |
| `p*` | Matches zero or more occurrences of the letter p. |
| `p?` | Matches zero or one occurrences of the letter p. |
| `p{2}` | Matches exactly two occurrences of the letter p. |
| `p{2,3}` | Matches at least two occurrences of the letter p, but not more than three occurrences. |
| `p{2,}` | Matches two or more occurrences of the letter p. |
| `p{,3}` | Matches at most three occurrences of the letter p |

The regular expression in the following example will splits the string at comma, sequence of commas, whitespace, or combination thereof using the JavaScript `split()` method:

#### Example

```javascript
var regex = /[\s,]+/;
var str = "My favourite colors are red, green and blue";
var parts = str.split(regex);

// Loop through parts array and display substrings
for(var part of parts){
    document.write("<p>" + part + "</p>");
}
```

* * *

## Position Anchors

There are certain situations where you want to match at the beginning or end of a line, word, or string. To do this you can use anchors. Two common anchors are caret (`^`) which represent the start of the string, and the dollar (`$`) sign which represent the end of the string.

| RegExp | What it Does |
| --- | --- |
| `^p` | Matches the letter p at the beginning of a line. |
| `p$` | Matches the letter p at the end of a line. |

The regular expression in the following example will match only those names in the names array which start with the letter "J" using the JavaScript `test()` function:

#### Example

```javascript
var regex = /^J/;
var names = ["James Bond", "Clark Kent", "John Rambo"];

// Loop through names array and display matched names
for(var name of names) {
    if(regex.test(name)) {
        document.write("<p>" + name + "</p>")
    }
}
```

* * *

## Pattern Modifiers (Flags)

A pattern modifier allows you to control the way a pattern match is handled. Pattern modifiers are placed directly after the regular expression, for example, if you want to search for a pattern in a case-insensitive manner, you can use the `i` modifier, like this: `/pattern/i`.

The following table lists some of the most commonly used pattern modifiers.

| Modifier | What it Does |
| --- | --- |
| `g` | Perform a global match i.e. finds all occurrences. |
| `i` | Makes the match case-insensitive manner. |
| `m` | Changes the behavior of `^` and `$` to match against a newline boundary (i.e. start or end of each line within a multiline string), instead of a string boundary. |
| `o` | Evaluates the expression only once. |
| `s` | Changes the behavior of `.` (dot) to match all characters, including newlines. |
| `x` | Allows you to use whitespace and comments within a regular expression for clarity. |

The following example will show you how to use the `g` and `i` modifiers in a regular expression to perform a global and case-insensitive search with the JavaScript `match()` method.

#### Example

```javascript
var regex = /color/gi;
var str = "Color red is more visible than color blue in daylight.";
var matches = str.match(regex); // global, case-insensitive match
console.log(matches);
// expected output: ["Color", "color"]
```

Similarly, the following example shows how to match at the beginning of every line in a multi-line string using the `^` anchor and `m` modifier with the JavaScript `match()` method.

#### Example

```javascript
var regex = /^color/gim;
var str = "Color red is more visible than \ncolor blue in daylight.";
var matches = str.match(regex); // global, case-insensitive, multiline match
console.log(matches);
// expected output: ["Color", "color"]
```

* * *

## Alternation

Alternation allows you to specify alternative version of a pattern. Alternation in a regular expression works just like the `OR` operator in an `if-else` conditional statement.

You can specify alternation using a vertical bar (`|`). For example, the regexp `/fox|dog|cat/` matches the string "fox", or the string "dog", or the string "cat". Here's an example:

#### Example

```javascript
var regex = /fox|dog|cat/;
var str = "The quick brown fox jumps over the lazy dog.";
var matches = str.match(regex);
console.log(matches);
// expected output: ["fox", index: 16, ...]
```

**Note:** Alternatives are evaluated from left to right until a match is found. If the left alternative matches, the right alternative is ignored completely even if it has a match.

* * *

## Grouping

Regular expressions use parentheses to group subexpressions, just like mathematical expressions. Parentheses allow a [repetition quantifier](#repetition-quantifiers) to be applied to an entire subexpression.

For example, in regexp `/go+/` the quantifier `+` is applied only to the last character `o` and it matches the strings "go", "goo", and so on. Whereas, in regexp `/(go)+/` the quantifier `+` is applied to the group of characters `g` and `o` and it matches the strings "go", "gogo", and so on.

#### Example

```javascript
var regex = /(go)+/i; 
var str = "One day Gogo will go to school.";
var matches = str.match(regex); // case-insensitive match
console.log(matches);
// expected output: ["Gogo", "go", index: 8, ...]
```

**Note:** If the string matches the pattern, the `match()` method returns an array containing the entire matched string as the first element, followed by any results captured in parentheses, and the index of the whole match. If no matches were found, it returns `null`.

**Tip:** If the regular expression includes the `g` flag, the `match()` method only returns an array containing all matched substrings rather than match object. Captured groups, index of the whole match, and other properties are not returned.

* * *

## Word Boundaries

A word boundary character ( `\b`) helps you search for the words that begins and/or ends with a pattern. For example, the regexp `/\bcar/` matches the words beginning with the pattern car, and would match cart, carrot, or cartoon, but would not match oscar.

Similarly, the regexp `/car\b/` matches the words ending with the pattern car, and would match oscar or supercar, but would not match cart. Likewise, the `/\bcar\b/` matches the words beginning and ending with the pattern car, and would match only the word car.

The following example will highlight the words beginning with car in bold:

#### Example

```javascript
var regex = /(\bcar\w*)/g;
var str = "Words begining with car: cart, carrot, cartoon. Words ending with car: oscar, supercar.";
var replacement = '<b>$1</b>';
var result = str.replace(regex, replacement);
document.write(result);
```

* * *