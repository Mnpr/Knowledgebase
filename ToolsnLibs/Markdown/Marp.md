# Markdown Presentation( Marp )

**Components :**

- Marpit Framework( Markdown -> Html slide deck )

- Marp Core

**Features :**

- Themes( Built-in | CSS )

- Inline SVG slide

- Common Mark

- KaTeX

- Emoji

- Size global Directive

- Autoscaling

**Applications :**

- Marp CLI

- Marp Web

**Integration :**

- VS code

- Marp ( React | Vue)

## @marp-cli

A CLI interface for Marp and any slide deck converter based on Marpit framework. it can convert Marp/ Marpit Markdown files into static HTML/ CSS, PDF, Powerpoint document, and Images easily.

#### Local Installation

```node
npm install --save-dev @marp-team/marp-cli
```

Then installed `marp` command is available in npm-script or `npx marp`

#### Global Installation

```node
npm install -g @marp-team/marp-cli
```

**Docker :**

[https://hub.docker.com/r/marpteam/marp-cli/](https://hub.docker.com/r/marpteam/marp-cli/)

#### Basic Usage

**Npx :**

```node
# Convert slide deck into HTML
npx @marp-team/marp-cli slide-deck.md
npx @marp-team/marp-cli slide-deck.md -o output.html

# Convert slide deck into PDF
npx @marp-team/marp-cli slide-deck.md --pdf
npx @marp-team/marp-cli slide-deck.md -o output.pdf

# Convert slide deck into PowerPoint document (PPTX)
npx @marp-team/marp-cli slide-deck.md --pptx
npx @marp-team/marp-cli slide-deck.md -o output.pptx

# Watch mode
npx @marp-team/marp-cli -w slide-deck.md

# Server mode (Pass directory to serve)
npx @marp-team/marp-cli -s ./slides
```

#### Conver to Html

```shell
marp slide-deck.md
marp slide-deck.md -o output.html
```

#### Convert to PDF

```shell
marp --pdf slide-deck.md
marp slide-deck.md -o converted.pdf
```

#### Convert to PPTX

```shell
marp --pptx slide-deck.md
marp slide-deck.md -o converted.pptx
```

#### Convert to PNG/ JPEG

```shell
# Convert into multiple PNG image files
marp --images png slide-deck.md

# Convert into multiple JPEG image files
marp --images jpeg slide-deck.md
```

## @marp-core

**The core of [Marp](https://github.com/marp-team/marp) converter.**
In order to use on Marp tools, we have extended from the slide deck framework [Marpit](https://github.com/marp-team/marpit) You can use the practical Markdown syntax, advanced features, and official themes.

## Usage

We provide `Marp` class, that is inherited from [Marpit](https://github.com/marp-team/marpit).

```javascript
import Marp from '@marp-team/marp-core'
// Convert Markdown slide deck into HTML and CSS
const marp = new Marp()
const { html, css } = marp.render('# Hello, marp-core!')
```

## Features

_We will only explain features extended in marp-core._ Please refer to [@marp-team/marpit](https://github.com/marp-team/marpit) repository if you want to know the basic feature of Marpit framework.

### Marp Markdown

Marp Markdown is based on [Marpit](https://github.com/marp-team/marpit) and [CommonMark](https://commonmark.org/), and there are these additional features:

- **Marpit**
  - Enable [inline SVG mode](https://github.com/marp-team/marpit#inline-svg-slide-experimental) and loose YAML parsing by default.
* **CommonMark**
  - For security reason, HTML tag only allows whitelisted elements by default.
  - Support [table](https://github.github.com/gfm/#tables-extension-) and [strikethrough](https://github.github.com/gfm/#strikethrough-extension-) syntax, based on [GitHub Flavored Markdown](https://github.github.com/gfm/).
  - Line breaks in paragraph will convert to `<br>` tag.
  - Auto convert URL like text into hyperlink.

## Built-in official themes

| Default                     | Gaia                        | Uncover                     |
|:---------------------------:|:---------------------------:|:---------------------------:|
| ![](https://bit.ly/2Op7Bp6) | ![](https://bit.ly/2QhDq4S) | ![](https://bit.ly/2DqZvvh) |
| `<!-- theme: default -->`   | `<!-- theme: gaia -->`      | `<!-- theme: uncover -->`   |

### `size` global directive

Do you want a traditional 4:3 slide size? We've added the support of `size` global directive only for Marp Core. Our extended theming system can use `960`x`720` slide in built-in themes easier: `size: 4:3`.

```markdown
---
theme: gaia
size: 4:3
---
# A traditional 4:3 slide
```

If you want to use more size presets in your theme, you have to define `@size` metadata(s) in theme CSS. [Learn in the document of theme metadata for Marp Core](https://github.com/marp-team/marp-core/blob/master/themes#metadata-for-additional-features). Theme author does not have to worry an unintended design being used with unexpected slide size because user only can use pre-defined presets by author.

### Autoscaling Features

Auto-scaling is available only if enabled [Marpit's `inlineSVG` mode](https://github.com/marp-team/marpit#inline-svg-slide-experimental) and defined [`@auto-scaling` metadata](https://github.com/marp-team/marp-core/blob/master/themes#metadata-for-additional-features) in an using theme CSS.

```css
/*
 * @theme enable-all-auto-scaling
 * @auto-scaling true
 */
```

Marp Core's scaling features will be realized by manipulating the 
original DOM to use inline SVG. So the theme author must take care of 
updated DOM in styling. Refer to [the source code of offical themes](https://github.com/marp-team/marp-core/blob/master/themes).

`@auto-scaling` meta can also pick the favorite features to enable by using keyword(s).

```css
/*
 * @theme enable-auto-scaling-for-fitting-header-and-math
 * @auto-scaling fittingHeader,math
 */
```

>  In the math block and the code block, Marp Core won't detect whether they actually protrude from the slide. It might not work scaling correctly when there are many elements in a slide.

#### Fitting header

When the headings contains `<!-- fit -->` comment, the size of headings will resize to fit onto the slide size.

```gfm
# <!-- fit --> Fitting header
```

This syntax is similar to [Deckset's `[fit]` keyword](https://docs.decksetapp.com/English.lproj/Formatting/01-headings.html), but we use HTML comment to hide a fit keyword on Markdown rendered as document.

>  `@auto-scaling fittingHeader` is a keyword of the `@auto-scaling` meta to enable fitting header.

#### Math block

We can scale-down the viewing size of math block (surrounded by `$$`) to fit a slide automatically.

>  `@auto-scaling math` is a keyword of the `@auto-scaling` meta to enable math block scaling.

### Code block

Several themes also can scale-down the viewing size of the code block to fit a slide. These features means that the contents on a slide are not cropped, and not shown unnecessary scrollbars in code.

>  `@auto-scaling code` is a keyword of the `@auto-scaling` meta to enable code block scaling.
> 
> `uncover` theme has disabled code block scaling because we use elastic style that has not compatible with it.

## Constructor options

You can customize a behavior of Marp parser by passing an options object to the constructor. You can also pass together with [Marpit constructor options](https://marpit-api.marp.app/marpit#Marpit).

> /unicode/2139.png) [Marpit's `markdown` option](https://marpit-api.marp.app/marpit#Marpit) is accepted only object options because of always using CommonMark.

```js
const marp = new Marp({  // marp-core constructor options
  html: true,  
  emoji: {    
      shortcode: true,
      unicode: false,
      twemoji: {      base: '/resources/twemoji/',}, 
  },
  math: { katexFontPath: '/resources/fonts/',  },
  minifyCSS: true,
  script: { source: 'cdn', nonce:'xxxxxxxxxxxxxxx',  },    
  // It can be included Marpit constructor options
  looseYAML: false,
  markdown: {    breaks: false,  },
})
```
