---
layout: post
title: Custom Bundler Configs
tags:
  - ruby
  - bundler
---

Custom Bundler Configs
===

Earlier today I was working in a legacy ruby environment, and ran into a system conflict with my local rubies. In short, `libv8` wasn't installing correctly, and my bundle was broken. This bundler was using `Rake 1.12.5` and `ruby-2.2.0`. 

Here's this problem pretty well documented online:

* [Github Issue](https://github.com/cowboyd/libv8/issues/205)
* [Stack Overflow](http://stackoverflow.com/questions/19673714/error-installing-libv8-error-failed-to-build-gem-native-extension)
* [Stack Overflow 2](http://stackoverflow.com/questions/27260199/libv8-3-16-14-3-fails-to-install-rails-4-1-8)

All of those solutions basically address the sole problem: **libv8 version conflicts**. But none of them address this through the bundle, all using the gem cli. I needed something I could push to a distributed environment.

The gem failures were based on `libv8` and `therubyracer`. I needed to link up the correct system v8 on install.

```
brew uninstall v8
brew install v8-315
```

The solutions would lead to tell me something like this: 

```
gem install libv8 -- --with-system-v8
gem install therubyracer -- --with-v8-dir=/usr/local/..
```

But I needed it via bundle, this I dug into [bundler configs](http://bundler.io/v1.3/man/bundle-config.1.html).

So to set this up via CLI, heres the command:

```
bundle config --local build.libv8 --with-system-v8
bundle config --local build.therubyracer --with-v8-dir=$(brew --prefix v8-315)
```

Which leads to...


```
---
BUNDLE_PATH: ".bundle/gems"
BUNDLE_BIN: ".bundle/bin"
BUNDLE_DISABLE_SHARED_GEMS: true
BUNDLE_BUILD__LIBV8: "--with-system-v8"
BUNDLE_BUILD__THERUBYRACER: "--with-v8-dir=/usr/local/opt/v8@3.15"

```

Boom... now I am installing legacy versions through bundler.
