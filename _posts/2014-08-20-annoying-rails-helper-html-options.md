---
title: Annoying rails select helper html options
---

If you've built rails apps this should seem familiar to you:

```ruby
<%= form_for @model do |d| %>
  <%= f.text_field :title, :class => "form-control" %>
<% end %>
```

but when you try to add the simple html elements to a select tag, you'll get some bs.


```ruby
<%= form_for @model do |f| %>
  <%= f.text_field :title, :class => "form-control" %>
  <%= f.select :title, :class => "form-control" %>
<% end %>
```

That's because the select tag takes different arguments, and you'll have to pass in the arguments accordingly.

```ruby
<%= select(:resource, :method, options: {}, html_options: {}, &block) %>
# resource is assumed
<%= f.select(:method, options: {}, html_options: {}, &block) %>
```

So in order to get your classes to work you have to pass in blank objects to options, and wrap your html_options in an object.

```ruby
<%= form_for @model do |f| %>
  <%= f.text_field :title, :class => "form-control" %>
  <%= f.select :title, {}, {:class => "form-control"} %>
<% end %>
```




