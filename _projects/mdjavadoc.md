---
layout: project
type: nodejs
title: "mdjavadoc"
description: "A script that generates markdown javadocs for use in Jekyll and GitHub Pages."
repo: TheAndroidMaster/mdjavadoc
git: git://github.com/TheAndroidMaster/mdjavadoc.git
links:
  - name: GitHub
    url: https://github.com/TheAndroidMaster/mdjavadoc
    icon: https://github.com/favicon.ico
  - name: Issues
    url: https://github.com/TheAndroidMaster/mdjavadoc/issues
    icon: /images/ic/bug.svg
  - name: MIT License
    url: https://choosealicense.com/licenses/mit/
    icon: /images/ic/copyright.svg
  - name: npm
    url: https://www.npmjs.com/package/mdjavadoc
    icon: https://www.npmjs.com/favicon.ico
contributors:
  - login: TheAndroidMaster
    avatar: https://avatars1.githubusercontent.com/u/13000407?v=4
    url: https://github.com/TheAndroidMaster
---

Markdown Javadoc is a script that generates markdown javadocs primarily for use in Jekyll and GitHub Pages. It consists of two modules, an [API](https://github.com/TheAndroidMaster/mdjavadoc/blob/master/./api/README.md) and [CLI](https://github.com/TheAndroidMaster/mdjavadoc/blob/master/./cli/README.md). If you simply want to generate a set of javadocs in markdown without any scripting, the CLI provides a simple interface with a decent amount of options. If you have a more complex use case, however, it might be more beneficial to look into the API first.

## Installation

These are generic installation instructions that are fairly similar for both the API and CLI. 

### NPM

```shell
npm install -g mdjavadoc
```

### From Source

```shell
git clone https://github.com/TheAndroidMaster/mdjavadoc
cd mdjavadoc/cli
sudo npm install -g
sudo npm link
```

For specific usage instructions, see the README for the [API](https://github.com/TheAndroidMaster/mdjavadoc/blob/master/./api/README.md) or [CLI](https://github.com/TheAndroidMaster/mdjavadoc/blob/master/./cli/README.md) components.

## Functionality

The program works by searching a set of files for [javadoc comments](https://www.oracle.com/technetwork/java/javase/documentation/index-137868.html), parsing them into a data structure containing the description, tags, and metadata, and then outputting that data into a set of markdown files. For example, a file containing a javadoc comment like the one below would yield the following structure and output...

##### Javadoc

```java
/**
 * This is a method which does a thing with something and stuff.
 * 
 * @param something		This is something.
 * @param stuff			This is a bunch of stuff.
 * @return			A thing.
 */
public static Object doTheThing(int something, String[] stuff) {
	return null;
}
```

##### Data

```javascript
[
  {
    name: "doTheThing",
    description: "This is a method which does a thing with something and stuff.",
    type: ["public", "static", "void"],
    source: "/package/structure/ClassName.java#L2",
    param: [
      {
        content: "@param something\tThis is something.",
        template: ["Parameter Name", "Description"],
        values: ["something", "This is something."]
      },
      {
        content: "@param stuff\t\tThis is a bunch of stuff.",
        template: ["Parameter Name", "Description"],
        values: ["stuff", "This is a bunch of stuff."]
      }
    ],
    return: [
      {
        content: "@return\t\tA thing.",
        template: ["Returned Value"],
        values: ["A thing."]
      }
    ]
  }
]
```

##### Markdown

```md
## [doTheThing](../blob/master/package/structure/ClassName.java#L2)

**Type:** `public` `static` `void`

This is a method which does a thing with something and stuff.

|Parameter Name|Description|
|-----|-----|
|something|This is something.|
|stuff|This is a bunch of stuff.|

**Returned Value:** A thing.
```

## Configuration

Aside from an input and output file/directory, the script has several options which you can specify to alter the output of the program.

| Option Name  | Type    | Description |
|--------------|---------|-------------|
| reg          | RegExp  | A regular expression to filter out unwanted files (defaults to `/^(?!\.).*/`, or "any file that does not begin with a `.`"). |
| regdir       | RegExp  | `reg` but for directories. |
| extensions   | boolean | Whether to include the file extensions in the generated content (setting this to true will name files "ClassName.java.md" instead of just "ClassName.md") |
| sourcePrefix | string  | A string to start all source code URLs with. Defaults to "..". For example, a link to "/api/index.js#L50" will become "../api/index.js#L50". |

## Contributing

Contributions are accepted. See this project's [CONTRIBUTING.md](https://github.com/TheAndroidMaster/mdjavadoc/blob/master/./.github/CONTRIBUTING.md) for instructions on how to contribute to this project.
