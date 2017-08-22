---
layout: post
title: Split Strings into chars ruby
tags:
  - ruby
---

Splitting strings into chars is a common programming application, especially if you're parsing a lot of text or reading line by line. Below is a couple examples from the other day I used to split strings in ruby.

```ruby
file_lines = File.readlines(File.join(__dir__, "/post.md"))

# parse H1 in md
file_lines.each do |line|
  line.chars[0] == "#" ? (format_h1) : (nil)
end

# remove H1 leading '#'
def remove_prefix(line)
  line.shift
end

# Pop the last char
def remove_last_char(line)
  line.pop
end
```


Nothing fancy, but useful if you were parsing markdown manually like I was. TC
