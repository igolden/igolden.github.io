---
title: MacDown App & a nice little alias
---

The other day I discovered [MacDown](https://macdown.uranusjr.com/), a markdown client for Mac. Since I work at a software consultancy that heavily utilizes jekyll and markdown for day to day communication, this was a _godsend_.

**Why use MacDown?**

In general, you have to push up your README.md files or any of your blog posts to see them fully formatted. That can be a pain in the ass when you're trying to check formatted lists, bullets, code, whatever in Github markdown. 

So _instead_, use [MacDown](https://macdown.uranusjr.com/) and view/edit your changes immediately. The split makes it easy to keep track of your source if you like the markdown editor.

But that wasn't good enough. MacDown has a CLI integration, which you can see here. Esentially the app ships with a binary your can use and symlink to create a global command. Here's the docs on that -> [Scroll a little less than halfway](https://macdown.uranusjr.com/blog/macdown-04/).

The docs will tell you to create a symlink like so:

```
sudo ln -s /Applications/MacDown.app/Contents/SharedSupport/bin/macdown /usr/bin
```

Running the above command failed for me, with "permission denied". And really I prefer to manage these symlinks via aliases in my `.zshrc`, so I ended up with this nice little alias:

```
# macdown
alias md="/Applications/MacDown.app/Contents/SharedSupport/bin/macdown"

# usage is simple
md <file>
```

Now I just use `md <file>` to open it up in MacDown. I love it.

