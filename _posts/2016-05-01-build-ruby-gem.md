Always Start Your Gems w/ Init
===

I've been building gems lately to script out some of my basic workflows. It's super easy, super powerful, and a lot of fun. I thought I'd share a few tips and tricks to get you rolling out your gem init.

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

Above are the files we care about.

* Sets up tests
* Basic rake file intialized
* Gemfile for packaging external services
* Sets up a module namespace



