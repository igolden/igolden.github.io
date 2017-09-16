---
title: Bundling a node module on github
---

Sometimes you need a quick and dirty way to share a node module. Just ran through this and thought I'd post it.

The easiest way to share a module is via github.

1. Package the module
2. Upload to git
3. Install with url


### Package the module

To package your module, set your entrypoint in package.json, and make sure you export the package however you'd like it to be consumed.


### Upload it Git

Push it up to git like always


### Install with url

To install via cli

```
npm i git+ssh://git@github.com/<author>/<repo>.git --save
```

Or add to package.json

```
"your-package-name": "git+ssh://git@github.com/<author>/<repo>.git",
```
