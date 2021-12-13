---
layout: post
title:  "Learning JavaScript"
date:   2021-08-06
category: L
tags: 
- Javascript
---
Recently I decided to learn Javascript. I had been avoiding it for a while now, trying to use Python and C++ wherever I could, partly because it was in my comfort zone, and partly because I had some kind of hatred towards web development in general. I carried a skewed view that web development is all about the HTML tags, CSS and all other design things, and that it was not "real" code.

But this changed, when I interned at Cloudanix. The web is a very complex environment and a lot happens in the background that we never pay attention to. All these systems, working like a clockwork, give us the privilege to make assumptions about the simplicity of it.

I am very fascinated with large-scale systems that serve millions of requests with almost real-time performance. Web being the base for these systems, it is important for me to understand it well.

Javascript is one of the starting points.

## How JavaScript Works

JavaScript is a **synchronous, single-threaded** language. JavaScript code is executed in what is known as an **Execution Context**. We can imagine it as a container, having two main parts:

- **Memory Part or Variable Environment**: Contains all the variables and their values in key-value pairs, and functions as well.
- **Code Part or Thread of Execution**: Code is executed here, one line at a time. 


### Hoisting in JavaScript

```javascript
//Code to Explain the concept of Hoisting

console.log(x);
sample();

function sample(){
    console.log("Hello World");
}

var x = 7;

```
**Hoisting** is the idea of pushing function and variable declarations to the top of code during 

