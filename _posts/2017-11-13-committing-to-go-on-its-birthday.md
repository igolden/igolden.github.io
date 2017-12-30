---
title: Comitting To Go Lang, on its 8th Birthday
layout: post
tags: 
  - update
  - golang
  - programming
---

In light of my [recent post](http://iangolden.com/2017/11/13/onward-2018-blogging.html), I thought I'd give some insight into a not-so-small decision I've made.

**I'm comitting to using the Go programming language professionally.**

Now, there's lots of articles sharing the praise of the Go programming language, and rightfully so. But this article will be more a _personal excerpt_ of my last few months, and how I ended up adopting (in process of) this young systems programming language.


### C++ and Game Engines

For the last few months, I've been writing a lot of game code. I find it challenging, fascinating, and ultimately rewarding when you can write code that impacts gameplay. All of the engines are built in C/C++, and then either expose C++ APIs (UE4), or allow scripting of the engine via C# (Unity).

C++ is great because of its power, bredth of use, and age. The creators are still working on the language, and that means a lot to me. The specification is thoroughly documented and there's literally enough information to pour over for years (think 1986 release).

Well this led me into...

### Code preferences change

I write ruby/js most of my days, and I have to say I _love_ statically typed code! It just clicks for me. This article is **not** about static vs dynamic typing systems. I just want to be clear that my last 3 months have been interesting, as I've realized something about myself. I prefer to read code with clearly documented types, and compiled languages favor that.


So, I start getting frustrated writing ruby. I start documenting types more. I even started building a simple ruby TypeChecking mixin to use as I need. Funny right?

### Ending up on Go

I've had my eye on Go for awhile now, but never felt the need to make the jump. With my day to day including more C++, I've found the need to reevalute the langauge as an option. Here's why I've made the decision:

* **Go is compiled, and portable**

  - coming from ruby, a big complaint of mine is installing the runtime on a new machine, and then managing that moving forward. Look - I get it - RVM! RBENV! CHRUBY! It's great. But sometimes I'd like to just download a binary, move it into my path and call it. Especially for devops tasks. Go solves that problem for me.

  - Go's also readily available on Windows/Mac/Linux. I can download the installer from their website and be up and running on any OS (i have machines with all 3 installed), and get back to work. The best part is, my vim setup will actually be useful!

* **Go is built by Ken Thompson (and other CS veterans), so yeah**

  - Ken Thompson worked side by side with Dennis Ritchie during the development of C and Unix. He's the father of Unix, and worked at Bell Labs up until 2006. Since '06 he's been working at Google, and began buiding Go sometime after that. Needless to say, if Ken thought it'd make sense to improve upon C, I believe him. I also believe there must've been a very important reason to improve upon our current language options, since he released the language at 66 (he's 74 now). So basically if Ken built it, I cosign it!

* **Vim support is vast**

  - Most of the times when I use a compiled language, it's very important that I setup my IDE (xcode/vscode/vs2017). Always a pain in the ass for a Vimmer. What are all these GUIs?? Y U NO WORK FAST?? Well go has an amazing vim plugin with tons of useful functionality, and a lot of the official go videos are livestreams using this plugin! I was instantly supportive of that and it helped me get up and running much faster.

* **Go HTTP Suppport + Revel**

  - Now, more relevant professional reasons. Most of my days are spent building API and a wide variety of clients. But at the end of the day, they all talk to some API. Go is awesome for APIs. Go HTTP is well documented as a high performant HTTP server. Revel is what interests me, a rails-like framework for Go. I long for structure, convention, etc that most compiled languages don't enforce (you should know what you're doing and how to organize software). Though I haven't used it, it seems to be well supported and in Go that will 'go' a long way.

* **Command Line Utilities**

  - Go has as ton of command line utilities, almost more than ruby now. gocui was what caught my interest, and I'm super interested in using that lib. The go toolset is a little bit of learning curve to non-nixers, but to me it was a welcome home. Just type the help command and start trying stuff.

* **Good Programming Habits**

  - Go makes you a better programmer in any language, plain and simple. A big qualm with ruby for me, is and was, learning ruby first. I mastered `each` blocks before I knew about control flow as a topic in a language. I never really got great at looping over numerical objects, without the range or `.times` operator. Now, ruby made all of that enjoyable no doubt, but I _couldn't transfer my knowledge of those ruby APIs over to other languages_. Shit even ruby abstracts public/private into attr_accessors/readers, and constructors into intialize. You almost never have to import stdlib files in rails, becuase they're all baked in.
  - Go again solves that. Go files will have all dependecies clearly imported. Go requires you manage your types, but if not, they will inferred in certain cases. Go offers traditional ways of declaring vars (literally `var c string = 'hello'`), along with syntactical sugar. Little utilities like their Time hierarchy etc have been a joy to come across.

* **STD LIB IS SICK!**

  - Go's STD LIB is heavy. There are some amazing tools baked right into Go, which you have to install in other languages. I'm talking crypto/http/more. Take the time a look for yourself.


---

Overall, I still have a **lot** to learn about the language of Go, but I've had fun writing a few little CLI apps and learning about what real problems I could solve with it. I started taking notes on Go's 8th birthday, when I realized that was the case. I took it as a sign and committed.

**Happy 8th Belated, Go :)**
