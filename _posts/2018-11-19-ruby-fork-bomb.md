---
title: Ruby Fork Bomb
layout: post
tags: 
  - ruby
  - unix
---


Was researching some interesting concepts in UNIX and came across an interesting form of DOS attack, the _fork bomb_.

Essentially a fork bomb infinitely loops over a command that forks a new process. In doing so you use up all the available memory on the machine. Leaving the commands here for future reference and notes on how to prevent.


In bash:

    :(){ :|: & };:


In ruby:

    ruby -e "loop { fork { bomb } }" &


In perl, available on mac:

    perl -e "fork while fork" &


To limit the max # of user forks, edit the `/etc/security/limits.conf` file. It's worth noting that `ulimit -u 100` will not prevent a fork bomb, as it only sets "soft" limits.


Good references here:

  * [http://gerardnico.com/wiki/linux/limits.conf](http://gerardnico.com/wiki/linux/limits.conf)
  * [http://www.cyberciti.biz/faq/understanding-bash-fork-bomb/](http://www.cyberciti.biz/faq/understanding-bash-fork-bomb/)
  * [http://www.cyberciti.biz/tips/linux-limiting-user-process.html](http://www.cyberciti.biz/tips/linux-limiting-user-process.html)

