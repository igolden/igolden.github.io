Colored Shell Output
===

If you work prodessionally in software development you've probably written some one-off shell scripts to help automate your workflow. This is something I do frequently.

A lot of times, it's nice to add a touch of color. You can do so below.


1. Create a function for color echo:

    cecho() {
      echo "${2}${1}${reset}"
      return
    }
    
    // usage
    cecho "WARNING: YOU ARE MAKING A CRITICAL CHANGE"

This is a simple function that allows you to toss a color flag as your last argument and it echoes the colored string.


* Add color list
* Functional example
* Share gist
