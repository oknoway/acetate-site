---
title: Acetate
active: documentation
layout: layouts/_documentation:content
---

# Configuration

Configuration is handled in the `acetate.conf.js` file. Besides setting where your source and build folders are, you can also set up environments, global variables, load extensions, configure `collections`, and ignore files.

## Basic Example

A basic working `acetate.conf.js` could look something like this:

```
module.exports = function (acetate) {
  acetate.global('config', {
    environment: 'dev'
  });

  acetate.layout('**/*', 'layouts/_layout:content');

  acetate.options.src = 'source/';
  acetate.options.dest = 'build/';
};
```

This does four things:

1. Creates a 'dev' environment. This is useful if you'd like to have multiple environments.
2. Assigns a default layout. All pages' content will be inserted into the content block of `layouts/_layouts.html`.
3. Sets the source folder. All source files will be kept in `source/`.
4. Sets the build folder. Running `acetate` will build the site to `build/`.

## Options

The `acetate.options` object can has a variety of properties you can set from the config. You set these in your `acetate.conf.js` by assigning the property to the string you'd like to use, like this:

```
acetate.options.src = 'source';
```

Properties on the options object you can set from the config:

| Setting     | Description                                   | Default |
| ----------- | --------------------------------------------- | ------------------ |
| dest        | Folder you'd like to build the site to        | `'build'` |
| src         | Folder containing the site's source files     | `'src'` |
| data        | Folder containing data files (json, js, yml)  | `'data'` |
| root        | Root directory for the acetate folder         | `process.cwd()` |
| markdownExt | RegEx for the markdown file extension         | <code>/\.(md&#124;markdown)/</code> |
| pageMatcher | Blob of all files that should become pages    | <code>**/*.+(md&#124;markdown&#124;html)</code> |
| dataMathcer | Blob of all files that can be site data       | <code>**/*.+(js&#124;json&#124;yaml&#124;yml)</code> |

# Global

# Layouts

# Options

# Collections