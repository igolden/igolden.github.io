---
layout: post
title: Increase your coding speed
tags:
  - productivity
  - misc
---

Let's face it. As a professional software engineer, and _especially_ a professional contract software engineer, the speed at which you work is important. We all hate it hear it, but it's the truth. And its the same reason managers are always arguing with developers about things they know nothing on... unit tests, devops, etc.

Before you start worrying about writing code faster, take care of your foundation:

* Write lots of tests (TDD helps)
* Study Your Language and know it's ins/outs
* Learn OOP, FP, and POP


Once you've gotten a good start, now you can implement a few tips and tricks to start customizing your workflow for speed.


### Use Custom Snippets

This is _key_. If you're not using [custom snippets](https://github.com/igolden/dotfiles/tree/master/vim/Ultisnips), you're wasting dozens of keystrokes every minute.

**What are snippets?**

Snippets are code bits that you can tab through with a shortcut. For example:

```
# Snippet to produce louder logging with '==='

snippet ===
puts "============================================================"
puts "== $1"
puts "============================================================"
endsnippet

# Snippet for defining a method in ruby
snippet def
def $1
  $0
end

```

Most editors have boilerplate snippets built in, but those aren't going to make you a badass. I'm a vimmer, so of course I want to customize my own. Start tracking the code bits you write multiple times a day and abstract all of them into custom snippets. Learn them, master them.


### Use Starter Projects

Some developers don't have the luxury of starting every project in a "Greenfield", or without any code at all. When you do start a new project, there's a ton of freedom because no decisions have been made for you yet. But once you have to setup 5 new projects in a week, you can instantly see the duplicated work.

Abstact your preferred dependencies into a start project and move it into Github. Always start your projects there. Maintain that project and change it just like your dotfiles.


### Use CLI Aliases

I don't care if you're not a terminal junky like me... you need to have an aliases file. Aliases allow you to set a command like 'hi' to run a different command or entire function/script.


### Muscle Memory

If you use vim, use chromium.
