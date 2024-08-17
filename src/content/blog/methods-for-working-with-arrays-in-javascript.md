---
author: Tom
pubDatetime: 2023-01-17T15:22:00Z
title: Methods for working with arrays in JavaScript
slug: methods-for-working-with-arrays-in-javascript
featured: false
draft: false
tags:
  - javascript
description:  In this post, I will show you some common methods for working with arrays in JavaScript.
---

- `push()` - adds an element to the end of an array
- `pop()` - removes the last element from an array
- `shift()` - removes the first element from an array
- `unshift()` - adds an element to the beginning of an array
- `splice()` - adds or removes elements from an array at a specified index
- `slice()` - returns a new array with a subset of elements from an original array
- `concat()` - combines two or more arrays into a new array
- `forEach()` - runs a function on each element of an array
- `map()` - creates a new array with the results of a function applied to each element of an original array
- `filter()` - creates a new array with elements that pass a test implemented by a provided function
- `reduce()` - applies a function against an accumulator and each element in the array (from left to right) to reduce it to a single value.
- `sort()` - sorts the elements of an array in ascending or descending order.

It\'s worth noting that many of these methods modify the original array, while others return a new array.

1. push() - adds an element to the end of an array
```javascript
let fruits = ["apple", "banana"];
fruits.push("orange");
console.log(fruits); // ["apple", "banana", "orange"]
```
2. pop() - removes the last element from an array
```javascript
let fruits = ["apple", "banana", "orange"];
fruits.pop();
console.log(fruits); // ["apple", "banana"]
```
3. shift() - removes the first element from an array
```javascript
let fruits = ["apple", "banana", "orange"];
fruits.shift();
console.log(fruits); // ["banana", "orange"]
```
4. unshift() - adds an element to the beginning of an array
```javascript
let fruits = ["banana", "orange"];
fruits.unshift("apple");
console.log(fruits); // ["apple", "banana", "orange"]
```
5. splice() - adds or removes elements from an array at a specified index
```javascript
let fruits = ["apple", "banana", "orange", "mango"];
fruits.splice(2, 1, "lemon", "kiwi");
console.log(fruits); // ["apple", "banana", "lemon", "kiwi", "mango"]
```
6. slice() - returns a new array with a subset of elements from an original array
```javascript
let fruits = ["apple", "banana", "orange", "mango"];
let citrus = fruits.slice(2);
console.log(citrus); // ["orange", "mango"]
```
7. concat() - combines two or more arrays into a new array
```javascript
let fruits = ["apple", "banana"];
let vegetables = ["carrot", "potato"];
let food = fruits.concat(vegetables);
console.log(food); // ["apple", "banana", "carrot", "potato"]
```
8. forEach() - runs a function on each element of an array
```javascript
let fruits = ["apple", "banana", "orange"];
fruits.forEach(fruit => console.log(fruit));
// apple
// banana
// orange
```
9. map() - creates a new array with the results of a function applied to each element of an original array
```javascript
let fruits = ["apple", "banana", "orange"];
let upperCaseFruits = fruits.map(fruit => fruit.toUpperCase());
console.log(upperCaseFruits); // ["APPLE", "BANANA", "ORANGE"]
```
10. filter() - creates a new array with elements that pass a test implemented by a provided function
```javascript
let fruits = ["apple", "banana", "orange", "mango"];
let longFruits = fruits.filter(fruit => fruit.length > 5);
console.log(longFruits); // ["banana", "orange"]
```
11. reduce() - applies a function
```javascript
let numbers = [1, 2, 3, 4, 5];
let sum = numbers.reduce((acc, curr) => acc + curr, 0);
console.log(sum); // 15
```
12. sort() - sorts the elements of an array in ascending or descending order.
```javascript
let fruits = ["orange", "apple", "banana"];
fruits.sort();
console.log(fruits); // ["apple", "banana", "orange"]
```
You can also sort an array of object by providing a comparator function
```javascript
let people = [  { name: "Alice", age: 30 },  { name: "Bob", age: 25 },  { name: "Charlie", age: 35 }];

people.sort((a, b) => a.age - b.age);
console.log(people);
// [{ name: "Bob", age: 25 },{ name: "Alice", age: 30 },{ name: "Charlie", age: 35 }]
```
Please note that sort() method sorts the elements of an array in ascending order by default, so if you want to sort it in descending order you need to provide a comparator function.