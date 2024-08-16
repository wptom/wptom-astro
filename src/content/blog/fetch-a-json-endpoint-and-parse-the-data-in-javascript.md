---
author: Tom
pubDatetime: 2022-12-26T15:22:00Z
title: Fetch a JSON endpoint and parse the data in JavaScript
slug: fetch-a-json-endpoint-and-parse-the-data-in-javascript
featured: false
draft: false
tags:
  - javascript
description: In this post, I will show you how to fetch a JSON endpoint and parse the data in JavaScript.
---

Here is an example of how to fetch a JSON endpoint and parse the data in JavaScript:
```javascript
fetch('https://api.example.com/endpoint')
.then(response => response.json())
.then(data => {
// do something with the data here
console.log(data);
});
```

In this example, we use the fetch function to send a request to the specified endpoint, and then we use the .then method to handle the response. The `response.json()` method parses the response as JSON, and the resulting data is passed as an argument to the callback function in the next .then block.

Inside the callback function, you can access the data and do whatever you want with it. For example, you could loop through the data and extract certain values, or you could use the data to update the content of a page.

It\'s important to note that this code uses asynchronous JavaScript, so the data may not be available immediately when the script runs. The .then method allows you to specify a callback function that will be called once the data is available.

Access particular data

To access particular data after fetching it from a JSON endpoint, you can use the dot notation or the bracket notation to access the properties of the JSON object.

1. Here is an example using the dot notation:
```javascript
   fetch('https://api.example.com/endpoint')
   .then(response => response.json())
   .then(data => {
   // access a property of the data object
   console.log(data.propertyName);
   });
```
2. Here is an example using the bracket notation:
```javascript
   fetch('https://api.example.com/endpoint')
   .then(response => response.json())
   .then(data => {
   // access a property of the data object
   console.log(data['propertyName']);
   });
```
In both examples, propertyName is the name of the property you want to access. You can also use variables with the bracket notation to access properties dynamically:
    
```javascript
fetch('https://api.example.com/endpoint')
.then(response => response.json())
.then(data => {
// access a property of the data object using a variable
let propertyName = 'name';
console.log(data[propertyName]);
});
```

You can also use these techniques to access properties of nested objects or arrays. For example:
```javascript
fetch('https://api.example.com/endpoint')
.then(response => response.json())
.then(data => {
// access a property of a nested object
console.log(data.object.property);

    // access an element of an array
    console.log(data.array[0]);
});
```