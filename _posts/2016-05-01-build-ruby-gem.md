---
title: Starting Gem builds with 'bundle init'
---

I've been building a lot of tiny gems lately to script out some basic stuff. It's super easy, super powerful, and a lot of fun. I thought I'd share a few tips and tricks to get you rolling out your gem init.

The basics:

Building a gem is simple. All your need to do is add a `.gemspec` file and file to call your methods from. But how do you grow a bundle?

```
bundle gem <gem_name>
```

This is going to spit out a nice little dir:

```
bin/
lib/
test/
your_gem.gemspec
Gemfile
Rakefile
...
```


Then... get to it. Having a dir structure is super important to me personally, so this gives me a big head start. I'm also a fan of cleaning the entire dir out if the script is only one file. But that's for another time. 
