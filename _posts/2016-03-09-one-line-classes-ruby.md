---
title: "Creating empty classes as oneliners"
---

I like to follow the community styleguide in ruby -> [Style Guide](https://github.com/bbatsov/ruby-style-guide)
Prefer a single-line format for class definitions with no body. [link]

```ruby
# bad
class FooError < StandardError
end

# okish
class FooError < StandardError; end

# good
FooError = Class.new(StandardError)
```
