---
title: Vim set nocompatible mode
---


This lil post is about a single setting in Vim that you'll see in just about every modern .vimrc.

```
set nocompatible
```


"nocompatible" is a mode that I feel most aren't familiar with, which is seeded in a lack of knowledge on the [history of Vim](https://en.wikipedia.org/wiki/Vim_(text_editor)).

**Vim** stands for Vi (Improved). *Essentially* all that means is Vim has modern tech built into it, Vi is antiquated and wonky. 

**Would anyone still prefer vi?**

Realistically, they shouldn't. But plenty of people will have to work with vi day to day, just because their OS or shell can't (or won't) run Vi(m).

So `set nocompatible` is described as such in the Vim docs:

```
This option has the effect of making Vim either more Vi-compatible, or make Vim behave in a more useful way.
```

You can see all of the the options related to nocompatible [here](http://vimdoc.sourceforge.net/htmldoc/options.html#'compatible').

Just wanted to illuminate the meaning behind something I see in every .vimrc (including mine), yet most people don't bother to look up.












