---
layout: post
title: URL params for logging into gmail/hangouts
tags:
  - misc
---

I'm basically always logged into 4-8 google accounts at any given time. Bouncing between hangouts, drive, and mail can be confusing and annoying. 


Super simple hack to choose your user in mail/hangouts/etc

```
https://hangouts.google.com/hangouts/_/bowtie.io/brainstorm?authuser=1_
```

```
// the param that matters
`?authuser=0`

// auth second account
`?authuser=1`

// auth third account
`?authuser=2`
```

That's the money right there. For gmail, it's just about as easy:

```
mail.google.com/mail/u/0/inbox
```



