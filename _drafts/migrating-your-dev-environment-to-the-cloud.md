---
layout: default
title: Moving Your Development Environment to the Cloud 
---

I recently moved all of my development environment assets to a remote cloud location (Google Drive). Change computers often for work? Then you need to do this. After you're done making the move, you'll be able to:

1. Setup your dev environment in under 30 min
2. Everytime you save a file, it is synced to cloud regardless of Git
3. Managing assets will become a BREEZE!
4. Move between devices seamlessly and stress-free 

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
* Notes Folder (I keep a notes folder in my home directory where I take notes in vim)

###Objectives
1. When changes are saved on device, they are synced to remote location.
2. On a new device, I can setup my entire environment in under 30 minutes.
3. Regardless of where I am, if I have internet access (4G LTE), I have access to everything I need.

So starting off, the very first objective will be completed by installing your cloud host on your computer. I will be using Google Drive for this example. 

**Quick Overview** - When you install Google Drive or Dropbox on your computer, it creates a local directory that mirrors your cloud-hosted folder. So essentially, if you add a file to this directory it will update the remote location as well, creating the sync result we need.


**Setting things up quickly** - Migrating your setup to a new computer can take hours upon hours if you have to manually install and compile all of the programs that make up your environment. Most (not all) CLI's and tools for development can be installed in any folder as long as the paths match up. We will act on that assumption moving forward.

**What are dotfiles?** - This post is not about dotfiles. But to clarify for the Jr. Dev's, dotfiles are your personal computer config options that effect your tools. My dotfiles address zsh (my shell), vim (my text editor), and git (source control).

So to avoid installing anything you to have to, we move all of the files into a folder called dotfiles (this name has no signifcance). My pseronal home directory looks something like this (simplified for ease).

{% highlight html %}

Home Directory
|_apps
|_websites
|_dotfiles
|_client-assets
|_notes

{% endhighlight %}


So the first thing we need to is represent all of these folders in the cloud somewhere. The dotfiles will be represented in a git repo, indefinitely. In another blog post I will go into the details behind the rake tasks within a dotfiles directory.
