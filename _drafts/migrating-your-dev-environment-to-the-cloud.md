---
layout: default
title: Moving Your Development Environment to the Cloud 
---

###Your Setup -- On Google Drive
This post is more about versatility and flexibility in your personal setup than anything. I want to take the time to overview how I've moved my setup to Google Drive over the last year, and why I chose to do so (besides the fact that 10TB's is only 9/mo).

###Why Did I Make the Move?
Over the last 3 years, I've had to purchase and sell more than 5 computers. That means that I've setup my personal setup WAY too many times. After computer 3 or 4, I started to move all of my dotfiles to bitbucket/github, and looked for ways to move my assets seamlessly between devices. Using Google Drive locally hosted folders and symlinks in my terminal, I was able to create a pretty effective setup that is hosted in the cloud.

###Why Google Drive?
Why not? Are you going to host on Dropbox? Be my guest, but with Google Drive I was able to keep everything centralized to my business email, but to each is own. 

Google Drive also has a fantastic API, which was my other motivation. If you're a newer developer, that won't be a game changer and any cloud service will work.

###Defining Your Assets
The first thing you need to do before you get started on moving to a commerical cloud setup is to define your assets. I needed to know what folders of mine I would be using daily within development. They were the following

+ Dotfiles (my zsh/vim/git/etc settings) 
+ Client Assets Folder (contains assets for projects)
* Websites Folder (contains source for my websites)
* Documents Folder (Various word/pages docs)
* Notes Folder (I keep a notes folder in my home directory where I take notes in vim)

###Objectives
1. When changes are saved on device, they are synced to remote location.
2. On a new device, I can setup my entire environment in under 30 minutes.
3. Regardless of where I am, if I have internet access (4G LTE), I have access to everything I need.



