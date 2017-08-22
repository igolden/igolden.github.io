---
layout: post
title: Using PostgreSQL Matchers in ActiveRecord
tags:
  - ruby
  - rails
  - postgres
---

The other day, I needed to search strings in my PostgreSQL database for substrings. This has since become a recurring pattern and I've been using it virtually every day now.


```
# Delete all example email users
User.where("email ~* ?", "example").delete_all

# Find specific User
User.where("email ~* ?", "jon@dough.com")

# Chained where calls
User.where("email ~* ?", "jon")
    .where("email ~* ?", "dough")
    .where("name ~* ?", "j")


```

Just a quick reminder for myself, and others. Take care!
