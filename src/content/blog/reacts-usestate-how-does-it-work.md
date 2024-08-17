---
author: Tom
pubDatetime: 2023-02-01T15:22:00Z
title: React's useState - how does it work?
slug: reacts-usestate-how-does-it-work
featured: false
draft: false
tags:
  - react
description:  In this post, I will explain how React's useState hook works and how you can use it in your applications.
---

`useState` is a hook in React that allows you to add state to your functional components. It returns an array with two elements: the current state value, and a function that updates it.

Here\'s an example to help illustrate its usage:

```jsx
import React, { useState } from 'react';

function Example() {
    const [count, setCount] = useState(0);
    
    return (
        <div>
            <p>You clicked {count} times</p>
            <button onClick={() => setCount(count + 1)}>
            Click me
            </button>
        </div>
    );
}
```

In this example, we\'re using `useState` to store the number of times a button has been clicked. The initial state value is 0. The `setCount` function is used to update the state when the button is clicked.

You can use useState with any type of value, not just numbers. For example, you can store an object:

```jsx
const [user, setUser] = useState({ name: 'John', age: 30 });

// later in your component:
setUser({ name: 'Jane', age: 25 });
```

or an array:

```jsx
const [todos, setTodos] = useState([{ text: 'Learn Hooks' }, { text: 'Build App' }]);

// later in your component:
setTodos([...todos, { text: 'Publish App' }]);
```

You can use multiple instances of useState in the same component to store different pieces of state.