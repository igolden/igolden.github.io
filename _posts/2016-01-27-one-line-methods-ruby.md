---
layout: post
title: "One line methods ruby"
categories: ["backpost", "ruby"]
---

One liners are key in any programming language. I'm come to like this syntax in ruby most:

```
def hello_world() p "hello world" end
```

Some people think that the lack of comma makes it hard to read, and I don't really agree. The parentheses are a nice visual queue for me, so I roll with that.

Here's a better example:

```
class FileManager
  def init(path, *new_path)
    @fpath = AGRV[1]
    @new_path = new_path if new_path
  end

  def rm() FileUtils.rm(@fpath) end

  def mv() FileUtils.mv(@fpath, @new_path) end

  def touch() FileUtils.touch(@fpath) end
end
```

I think those single like methods look easy to read, and give a slick "ruby-like" swag to them.

I use the Ruby style guide -> [Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide)
