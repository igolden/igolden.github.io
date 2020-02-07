---
title: Decrypting GPG files in node js
layout: post
tags: 
  - node
  - gpgk
---


I use GPG for most of my personal encryption. Basically, if i need to have a sensitive file sit at rest on my hard drive, i like to have it encrypted with GPG. Recently, I had a sqlite DB file that was encrypted with GPG for transport. It's not updated frequently, but it holds private information (not necessarily sensitive). Thus, it was encrypted.


So i want to access this DB via some node scripts. Turns out, like most things in the JS world, there's a package for that and it's quite easy to use.


### Setup

1. Install GPG
  
    brew install gnupg


2. Setup your primary key


This step can be confusing if you've never encrypted anything. If that's the case I'd suggest installing a GUI application for GPG on your OS. 

  - Mac: [https://gpgtools.org/](https://gpgtools.org/)
  - Windows: [https://scand.com/products/wingpg/](https://scand.com/products/wingpg/) (never used)
  - Linux (KDE): [https://utils.kde.org/projects/kgpg/](https://utils.kde.org/projects/kgpg/) (KDE)
  - Linux (GNOME): [https://wiki.gnome.org/Apps/Seahorse](https://wiki.gnome.org/Apps/Seahorse) (GNOME)



3. Install `node-gpg` in project.

    npm i gpg


Now that your GPG file is setup globally, you can just use a simple method to decrypt files!

    gpg.decryptToFile(
      {
        source: "./secrets.json.gpg",
        dest: "./secrets.json",
      },
      (err, success) => {},
    );


EZPZ.

