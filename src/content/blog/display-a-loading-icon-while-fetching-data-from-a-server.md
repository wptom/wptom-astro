---
author: Tom
pubDatetime: 2022-12-27T15:22:00Z
title: Display a loading icon while fetching data from a server
slug: display-a-loading-icon-while-fetching-data-from-a-server
featured: false
draft: false
tags:
  - javascript
  - css
description:  In this post, I will show you how to display a loading icon while fetching data from a server using JavaScript and CSS.
---

To display a loading icon while fetching data from a server, you can use a combination of HTML, CSS, and JavaScript. Here is an example of how you might do this:

First, create an HTML element to hold the loading icon. This could be an img element, a div element with a background image, or any other element that you want to use to display the icon. For example:
```html
<div id="loading">
  <img src="loading.gif" alt="Loading..." />
</div>
```
Next, use CSS to style the loading element and position it on the page. For example:
```css
#loading {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```
Finally, use JavaScript to show and hide the loading element when appropriate. You can do this by modifying the element\'s style property or by adding and removing classes with the classList property. For example:
```javascript
fetch('https://api.example.com/endpoint')
  .then(response => {
    // show the loading icon
    document.getElementById('loading').style.display = 'block';
    return response.json();
  })
  .then(data => {
    // hide the loading icon
    document.getElementById('loading').style.display = 'none';

    // do something with the data here
    console.log(data);
});
```
In this example, we use the fetch function to send a request to the server, and then we show the loading element before the response is received. Once the response is received and the data is parsed, we hide the loading element and do something with the data.

Two more examples

Example 1: Using classList property
```html
<div id="loading" class="hidden">
  <img src="loading.gif" alt="Loading..." />
</div>
```
```css
#loading {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```
```css
.hidden {
display: none;
}
```
```javascript
fetch('https://api.example.com/endpoint')
.then(response => {
// show the loading icon
document.getElementById('loading').classList.remove('hidden');
return response.json();
})
.then(data => {
// hide the loading icon
document.getElementById('loading').classList.add('hidden');

    // do something with the data here
    console.log(data);
});
```

In this example, we use the classList property to add and remove the hidden class from the loading element. The classList property is a collection of all the classes applied to an element, and it provides methods for adding, removing, and toggling classes.

Example 2: Using visibility property
```html
<div id="loading">
  <img src="loading.gif" alt="Loading..." />
</div>
```
```css
#loading {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  visibility: hidden;
}
```
```javascript
fetch('https://api.example.com/endpoint')
  .then(response => {
    // show the loading icon
    document.getElementById('loading').style.visibility = 'visible';
    return response.json();
  })
  .then(data => {
    // hide the loading icon
    document.getElementById('loading').style.visibility = 'hidden';
    });
```
Which solution is best?

It\'s difficult to say which solution is best because it depends on your specific requirements and the context in which you are using it. Here are a few things to consider when deciding which solution to use:

If you want to maintain a consistent layout while the loading icon is displayed, you may want to use a solution that doesn\'t alter the layout of the page. In this case, using the visibility property or the classList property with a class that sets display: none might be a good option.
If you don\'t need to maintain a consistent layout, you might prefer to use the display property because it allows you to completely hide the element and free up the space it occupies.
If you need to support older browsers that don\'t have native support for the fetch function, you may need to use a polyfill or a library like jQuery to make the code work. In this case, you might want to use a solution that is compatible with these libraries.

Ultimately, the best solution will depend on your specific needs and the context in which you are using it. I recommend experimenting with different approaches and seeing which one works best for your situation.