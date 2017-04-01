---
title: Moving Your Development Environment to the Cloud 
---

I recently moved all of my development environment assets to a remote cloud location (Google Drive). Do you change devices often for work? Then you need to do this. After you're done making the move, you'll be able to:

1. Setup  and install your development environment in under 30 min
2. Everytime you save a file, it will be synced to cloud regardless of using source control
3. Managing assets will become a BREEZE!
4. Move between devices seamlessly and stress-free 

### Your Setup -- On Google Drive
This post is more about creating versatility and flexibility in your personal setup than anything. I want to take the time to overview how I've moved my personal setup to Google Drive over the last year, and why I chose to do that.

### Why Did I Make the Move?
Over the last 3 years, I've had to purchase dozens computers/devices. That means that I've setup my personal setup WAY too many times. After computer 3 or 4, I moved all of my dotfiles to bitbucket/github. After an external drive blew out on me, I looked for ways to host my assets and move them seamlessly between devices. Using Google Drive's locally hosted folders, I was able to create an efficient setup that is hosted in the cloud.

### Why Google Drive?
Why not? Are you going to host on Dropbox? Be my guest, but Google Drive allowed me to keep everything centralized in my business email. Google Drive also has a fantastic API, which was my other motivation. If you're a newer developer, that won't be a game changer and any cloud service will work. 

*Side Note - I developed an app using carrierwave-dropbox gem and it was hell to finish. We actualy migrated to carrierwave-aws because the Dropbox API was not awesome. So these factors contributed to my decision.*

### Defining Your Assets
The first thing you need to do before getting started on migrating to a cloud setup is to define your assets. I needed to know what folders of mine I truly use during development. They were the following:

+ /dotfiles (my zsh/vim/git/etc settings) 
+ /client-assets (contains assets for projects)
* /websites (contains source for my websites)
* /notes (I keep a notes folder in my home directory where I take notes in vim)

### Objectives
Ultimately, the criteria below is how i judged the success of the migration.

1. When changes are saved on a device, they are synced to remote location.
2. On a new device, I can setup my entire environment in under 30 minutes.
3. Regardless of where I am, if I have internet access (4G LTE), I have access to everything I need.

So starting off, the very first objective will be completed by installing your cloud host on your computer. I will be using Google Drive for this example. 

**Quick Overview** - When you install Google Drive or Dropbox on your computer, it creates a local directory that mirrors your cloud-hosted folder. If you add a file to this directory it will update the remote location as well, creating the sync result we need.


**Setting things up quickly** - Migrating your setup to a new computer can take hours upon hours if you have to manually install and compile all of the programs that make up your environment. Most (but not all) CLI's and tools for development can be installed in any folder as long as the necessary paths match up with your commands. We will act on that assumption moving forward.

**What are dotfiles?** - This post is not about dotfiles. But to clarify for the Jr. Dev's, dotfiles are your personal computer config options that effect your tools. My dotfiles address zsh (my shell), vim (my text editor), and git (source control).

So to avoid reinstalling anything you to don't have to, we move all of the files into a folder called dotfiles (this name has no signifcance, but is industry standard). 

For a fantastic set of start dotfiles, check our Gary bernhardt's dotfiles.

The only thing that is required of your dotfiles to meet our objectives, is a setup command. In my personal dotfiles, I use a rake task to create the symlinks needed to my relative dotfiles. For those that need guidance here, google dotfiles setup and you'll get going. Rake files are a great first project for a new ruby developer that will help them understand automating tasks. In another blog post I will go into the details behind the rake tasks within a dotfiles directory. 

My personal home directory looks something like this (simplified for ease, does not include Documents, Desktop, etc).

{% highlight html %}

Home Directory
|_apps
|_websites
|_dotfiles
|_client-assets
|_notes

{% endhighlight %}


**First things first** - So the first thing we need to do is represent all of these folders in the cloud somewhere. The dotfiles will be represented in a git repo, so we don't have to put those in our cloud host. 




**Migrating Your Projects Folder**
To move your projects folder to an external cloud location, you have to look at your projects folder architecture. If you're keeping your projects directory clean (i.e. managing them all through git and deleting folders as you finish for the day) then you won't actually hugely benefit from this step. In our workflow, we have a 'websites' and 'apps' folder depending on the type of development we are using (jekyll vs. rail). So for me, git isn't the only tool we use to manage our assets. Ultimately we nede to keep all of our website asssets perpetually for our clients, just in case two years later they need some changes.

**Symlinks -- AKA Organizational Crackrocks** - Get addicted.

Symlinks are Symbolic Links that allow you to create direct links to project folders that may be nested deeper within your system. 

For example, I have a friend who keeps his projects under a structure like this:

{% highlight html %}

Home Directory
|_Documents
  |_Web
    |_Assets
      |_Projects
        |_ Development
        |_ PHP
        |_ Websites
        |_ Misc
{% endhighlight %}

Well that is CD Hell (change directory hell) if you want to navigate to that folder on a whim. More importantly, when we pair programmed, it took me even longer to get used to accessing his assets. ***So for the record --- it is very important to have a simple, accesible projects directory if you plan on pair programming regularly***. 

If you **don't** pair up often... then start. You're not winning if you're not pairing.

**Symlinking Your Directories** - A symlink is easy enough to create, and you can actually do it through Finder. But I would never reccomend that (death to Finder!!! pirate voice... yearrrgh). 

To symlink a directory though finder, check out this link:: <link here>

To symlink like a real boss, do it through the terminal: 

{% highlight html %}
ln -s /path/to/file/ /path/to/symlink/
{% endhighlight %}


### Linking this all together
Now that you understand the remote host setup, and we understand symlinks, you can link everything together to migrate seamlessly. Remember, we want this to be *silky smooth*. What's left?

1. Make all of development directories link to a folder in the home directory, making them accesible through the Shell's intiial command line location.
2. Migrate your assets to the symlinked folder in Drive, if you didn't already.

Now that you have setup Google Drive (or an alternative cloud interface) you will be autosyncing with the cloud everytime you save a file. To make this realistic in a dev environment, you need to make those folders be *simple, accesible, and high up in your directory structure.* Take a look at my default structure I listed earlier to get an idea:

{% highlight html %}

Home Directory
|_apps
|_websites
|_dotfiles
|_client-assets
|_notes

{% endhighlight %}

So for me to transfer those links to a cloud hosted alternative I need to do two things:

1. Setup the equivalent folder in Google Drive, and migrate my assets to that folder. 
2. Symlink to that folder so i don't know the difference.

Here are the symlinks I used:


{% highlight html %}

ln -s /Google\ Drive/apps apps
ln -s /Google\ Drive/websites websites
ln -s /Google\ Drive/client-assets client-assets
ln -s /Google\ Drive/notes notes

{% endhighlight %}

Remember, your dotfiles are in Git. At this point, when I open up iTerm and see a new shell. If I type in "cd websites" I will see no difference between this new setup and my old setup. The terminal represents symlinks as if they are real folders, but serve the contents of the symbolically linked folder. I am synced everytime I save a file (not accounting for sync time) accesible through the Google Drive app.

So that means... 

1. Steal my computer? Dont care. I'll cop a new one and be up and running in a day.
2. Have a new project? Clone it to your websites or apps folder and it links to Google Drive. MONEY.
3. Done with a project for good? Delete it from your websites directory and it actually deletes it from your Drive folder. That basically gives your command-line control of your Google Drive assets.

Have fun with this, and make sure your sh*t is accessible. In the words of a very, very wise person...


{% highlight html %}
AINT NOBODY GOT TIME FO' DAT!!!
{% endhighlight %}

Take care.
