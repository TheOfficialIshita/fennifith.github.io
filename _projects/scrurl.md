---
layout: "project"
type: "website"
title: "Scrurl"
description: "Scrolling urls, a.k.a. the second worst website I've ever made."
repo: "fennifith/Scrurl"
git: "git://github.com/fennifith/Scrurl.git"
links: 
  - name: "GitHub"
    url: "https://github.com/fennifith/Scrurl"
    icon: "https://github.com/favicon.ico"
  - name: "Issues"
    url: "https://github.com/fennifith/Scrurl/issues"
    icon: "/images/ic/bug.svg"
  - name: "Apache License 2.0"
    url: "https://choosealicense.com/licenses/apache-2.0/"
    icon: "/images/ic/copyright.svg"
  - name: "Website"
    url: "https://jfenn.me/Scrurl/"
    icon: "https://jfenn.me/images/favicon-32.ico"
contributors: 
  - login: "fennifith"
    avatar: "https://avatars1.githubusercontent.com/u/13000407?v=4"
    url: "https://github.com/fennifith"
languages: 
  - "HTML"
  - "JavaScript"
isDocs: "false"
isWiki: "false"
pushed: "2018-09-21T02:42:29Z"
---

Probably one of the worst things I've ever used my free time for, [this](https://jfenn.me/Scrurl/) is a script that displays scrolling text in the address bar. It is almost entirely useless. Please do not use it for anything. That said, if you want to make it any worse than it already is, please feel free to make a PR.

If for some reason you wish to change the message that scrolls in the url, simply prefix the query with an '@' symbol, for example: [https://jfenn.me/Scrurl/?@this_is_a_different_message](https://jfenn.me/Scrurl/?@this_is_a_different_message).

## Usage

If you for some reason do want to use this project in your own website, here's a quick guide to using it.

### Define the Script Tag

```html
<script type="text/javascript" src="https://jfenn.me/Scrurl/scrurl.js"></script>
```

### Start the Scrolly Thing

```javascript
Scrurl.display("a bunch of text", {
  "scrolldelay": 200, //the delay (in ms) between each scroll update
  "scrollamount": 1,  //the amount of characters to scroll on each update
  "direction": "left" //the direction to scroll through the characters in
});
```

### Stop the Scrolly Thing
This will stop the url from scrolling, but will not remove it from the address bar, because frankly I'm just too lazy to do that, and I don't think anyone will use it if I do.

```javascript
Scrurl.display(null);
```

### Sample Implementations

- [Literally the simplest implementation possible](https://github.com/fennifith/Scrurl/blob/master/./examples/simple.js)
- [Preventing Scrurl from interfering with address bar input](https://github.com/fennifith/Scrurl/blob/master/./examples/focusable.js)
