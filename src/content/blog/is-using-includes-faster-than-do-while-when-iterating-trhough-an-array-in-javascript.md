---
author: Tom
pubDatetime: 2023-01-27T15:22:00Z
title: Is using includes() faster than do-while when iterating trhough an array in Javascript?
slug: is-using-includes-faster-than-do-while-when-iterating-trhough-an-array-in-javascript
featured: false
draft: false
tags:
  - javascript
description:  When iterating through an array in JavaScript, is using the includes() method faster than using a do-while loop? Let's find out.
---

When iterating through an array in JavaScript, the fastest method will depend on the specific use case and the size of the array.

In general, if you are looking for a specific element in an array and you want to know if the element exists in the array, the `Array.prototype.includes()` method will be faster than using a do-while loop.

On the other hand, if you need to perform a specific operation on each element of the array and you need to have the index of the current element, then using a for-loop or forEach will be faster than `includes()` method.

So, it is recommended to use the appropriate method based on your specific use case and the size of the array.