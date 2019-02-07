---
layout: "project"
type: "undefined"
title: "Screenshot Maker"
description: "A small java applet to generate uniform Play Store screenshots with titles and descriptions."
repo: "fennifith/ScreenshotMaker"
git: "git://github.com/fennifith/ScreenshotMaker.git"
links: 
  - name: "GitHub"
    url: "https://github.com/fennifith/ScreenshotMaker"
    icon: "https://github.com/favicon.ico"
  - name: "Issues"
    url: "https://github.com/fennifith/ScreenshotMaker/issues"
    icon: "/images/ic/bug.svg"
  - name: "Apache License 2.0"
    url: "https://choosealicense.com/licenses/apache-2.0/"
    icon: "/images/ic/copyright.svg"
  - name: "ScreenshotMaker.jar (v1.2 stable)"
    url: "https://github.com/fennifith/ScreenshotMaker/releases/download/v1.2/ScreenshotMaker.jar"
    icon: "/images/ic/download.svg"
contributors: 
  - login: "fennifith"
    avatar: "https://avatars1.githubusercontent.com/u/13000407?v=4"
    url: "https://github.com/fennifith"
languages: 
  - "Java"
isDocs: "true"
isWiki: "false"
pushed: "2018-10-18T19:31:37Z"
---

ScreenshotMaker is small java applet used to generate uniform Play Store screenshots with titles and descriptions with minimal effort.

![img](https://github.com/fennifith/ScreenshotMaker/blob/master/./.github/images/main.png?raw=true)

## Installation

You might need to install [some recentish version of Java](https://java.com/en/download/). After that, you can grab a .jar file from [here](https://github.com/TheAndroidMaster/ScreenshotMaker/releases/).

### System Requirements

I've only just gotten this thing to work on my laptop (a beautiful ThinkPad T520 running Arch Linux), so I have no idea what the requirements are. I have tested it a little on Windows, and although there are a few issues (all file chooser dialogs go to System32, and none of them restrict the file extensions like they're supposed to), it seems to be usable.

### Creating a Desktop Entry

On most versions of Linux, you can create a desktop entry that will appear in whatever version of start menu your desktop environment uses by going to "file -> create desktop entry" and waiting for the ridiculously ugly confirmation dialog to appear. If you have followed instructions [like these](https://wiki.archlinux.org/index.php/fprint) to set up a fingerprint sensor as an alternative to entering your password for the sudo command, you may need to swipe your fingerprint before the dialog will appear. I don't know why this happens. I don't know what I'm doing. I'm bad at things.

## Usage

Simply enter a title, description, pick your colors and other preferences, choose a 16:9 screenshot to put in the frame, and hit "export image" to choose a location to save your screenshot.

### Saving Templates

You can save sets of preferences as ".sm" files for easier use in the future by going to "file -> save as", then "file -> open" when you next want to use it.
