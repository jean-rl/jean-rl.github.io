---
title: "Post Template"
date: 2020-09-15T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["first"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: false
# TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Desc Text."
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
# UseHugoToc: true
---

## This is the first post

Here I will talk about how I configured the custom font for my title.

You can *override* the CSS.
The css to override is at themes/assets/css/fonts.css

As you see, the font is loaded using a `.woff` file.

## Hei

```css
/* abril-fatface-regular - latin */
@font-face {
  font-family: 'Abril Fatface';
  font-style: normal;
  font-weight: 400;
  src: local(''),
       url('/fonts/abril-fatface-v19-latin-regular.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
       url('/fonts/abril-fatface-v19-latin-regular.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
}

```
### Download new fonts

Search for a font. A great one is [Google Fonts](https://fonts.google.com/). When finding the right font, search for its `.woff` and `.woff2` files in google. These are webfonts formats.

I downloaded the [Lalezar-Regular](https://github.com/BornaIz/Lalezar/tree/master/fonts/webfonts) font. 

To "install it", create the `assets/css/fonts.css` file. There, place the new font as:

```css
@font-face {
  font-family: 'Lalezar-Regular';
  font-style: normal;
  font-weight: 400;
  src: local(''),
    url('/fonts/Lalezar-Regular.woff2') format('woff2'),
    url('/fonts/Lalezar-Regular.woff') format('woff');
}
```

Then, create the `custom.css` file in the same folder and use it.

```css
.sidebar-about h1 {
  font-size: 1.4em;
  font-family: "Lalezar-Regular", monospace;
}
```

> Remember to include all the fonts defined in the theme's `fonts.css` file in this new file.