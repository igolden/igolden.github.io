---
title: Ruby shorthand statements
---

Ruby has a few ways to write shorthand if/else and control flow statements. I've really come to like JS's shorthand statements, and have since adopted oneliners in ruby wherever I can. Just putting this code here for reference later.

```ruby
# Bad
if 1 > 0
  p "Hello World."
end

# Good
p "Hello World" if 1 > 0


# Good, with nil else condition
1 > 0 ? (p "Hello World") : nil

# Good, with else condition
1 > 0 ? (p "Hello World") : (p )

# ERB
<%= "Hello World" if 1 > 0 %>
```

Only gotcha is wrapping the conditional functions in parentheses.
