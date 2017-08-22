---
layout: post
title: "Creating empty classes as oneliners"
tags:
  - ruby
---

I like to follow the community styleguide in ruby -> [Style Guide](https://github.com/bbatsov/ruby-style-guide)

Particularly, I like the single-line class definitions rule.

It's known that this looks terrible. No effort to clean up space:

```
class FooError < StandardError
end
```


Working with others, I see the 'okish' one-line version all of the time: 

```
class SomeClass < RuntimeError; end
```


But I always give a silent nod to anyone that I see using the simpler choice:

```
FooError = Class.new(StandardError) 
```

Again, this is all from the community style guide -> [Style Guide](https://github.com/bbatsov/ruby-style-guide)

