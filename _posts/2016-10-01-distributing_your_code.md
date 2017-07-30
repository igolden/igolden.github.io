---
title: Ways to Distribute Your Code
---

There's a lot of ways to distrubute code. In this post, I care most about portablity and least about ease of use.


### npm/gem/pip/cocoa/etc, the highest level dist.

These ae your high level distributions. Users of this package will have access to, at the very least, a
full virtual machine that they can provision as needed to run your package.

### linux/ubuntu/brew, OS packages. 

A little bit lower level. These packages are directly installed as executables in your operating system
(usually usr/local/bin). They can then be directly accessed form the CLI.

### Shell Scripts

What's more portable than OS packages? Simple shell scripts. All OSs are going to have a shelll and 
really just represent a cimplex interaction with the shell. Being able to paste a single file into
the shell and run it is incredibly powerful, and super portable.

### From Memory

The most portable way to distribute code: from memory. No dependencies (besides your lang, compiler, etc)
Pop into any terminal and start working. The more you write, the more you remember!



