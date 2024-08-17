---
author: Tom
pubDatetime: 2023-01-19T15:22:00Z
title: Using map method in Javascript
slug: using-map-method-in-javascript
featured: false
draft: false
tags:
  - javascript
description:  In this post, I will show you how to use the map method in Javascript to transform elements in an array.
---

The `map()` method in JavaScript is used to create a new array with the results of calling a provided function on every element in the calling array. Here are a few examples:

Multiplying each element in an array by 2:
```javascript
let numbers = [1, 2, 3, 4, 5];
let doubledNumbers = numbers.map(function(number) {
return number * 2;
});
console.log(doubledNumbers); // [2, 4, 6, 8, 10]
```
Getting the square of each element in an array:
```javascript
let numbers = [1, 2, 3, 4, 5];
let squaredNumbers = numbers.map(function(number) {
return number * number;
});
console.log(squaredNumbers); // [1, 4, 9, 16, 25]
```
Extracting properties from an array of objects:
```javascript
let users = [
{ name: 'John', age: 30 },
{ name: 'Jane', age: 25 },
{ name: 'Bob', age: 35 }
];
let names = users.map(function(user) {
return user.name;
});
console.log(names); // ['John', 'Jane', 'Bob']
```
Using arrow function
```javascript
let numbers = [1, 2, 3, 4, 5];
let squaredNumbers = numbers.map( number => number * number);
console.log(squaredNumbers); // [1, 4, 9, 16, 25]
```

Note that the `map()` method does not modify the original array, it returns a new array with the modified elements.