---
layout: post
title: "FileUtils -- #touch"
tags:
  - ruby
---

Was on the FileUtils docs the other day, found a neat little 'shell-like' method in ruby.

```
# Create a blank .vimrc
FileUtils.touch('/Users/igolden/.vimrc')
```

Could come in handy for scripting personal setups, provisioning on a server, or setting up a Docker container. Not something I'll use often, but cool to know more ruby secrets.

