---
title: React & React Native without snippets is absolute madness
---

I've been writing React for a couple years now. It's a fantastic abstraction of state into the UI, and I love the component lifecycle as a tool to hook into different events that adjust that state. I have to say that there's one thing that annoys the shit out of me.. duplicate code.

Every single component file will follow this pattern:

```js
// imports

// component definition
  // constructor
  // additional functions (componentDidUpdate, componentWillUpdate, etc)
  // render function

// styles
```

That pattern is particularly enforced a little more in React Native (at least in my projects).

