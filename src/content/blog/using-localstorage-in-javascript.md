---
author: Tom
pubDatetime: 2023-01-25T15:22:00Z
title: Using localStorage in Javascript
slug: using-localstorage-in-javascript
featured: false
draft: false
tags:
  - javascript
description:  In this post, I will show you how to create a national flag by using CSS gradient.
---

JavaScript provides the `localStorage` and `sessionStorage` objects, which can be used to store key-value pairs of data in the browser. The difference between the two is that localStorage stores data permanently, while sessionStorage stores data for a single session (data is lost when the browser tab is closed).

Here are a few examples of how to use localStorage to store JSON data:

## JavaScript
```javascript
// Store data
localStorage.setItem('myData', JSON.stringify({name: 'John', age: 30}));

// Retrieve data
let data = JSON.parse(localStorage.getItem('myData'));
console.log(data.name); // 'John'
console.log(data.age); // 30

// Remove data
localStorage.removeItem('myData');
```

It\'s important to note that the data stored in localStorage is limited to strings, so you need to use `JSON.stringify()` to convert your JSON object to a string when storing it, and `JSON.parse()` to convert it back to an object when retrieving it.

Also, localStorage is a client side storage, it\'s not recommended to store sensitive data in the localstorage, as it can be accessed by any script running on the same origin.