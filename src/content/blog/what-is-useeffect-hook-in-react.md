---
author: Tom
pubDatetime: 2023-02-15T15:22:00Z
title: What is useEffect hook in React?
slug: what-is-useeffect-hook-in-react
featured: false
draft: false
tags:
  - react
description:  In this post, I will explain what the useEffect hook is in React and how you can use it in your applications.
---

`useEffect` is a built-in React hook that allows you to manage side effects in functional components. Side effects are actions that occur outside the scope of a component and are not related to rendering, such as making an API call, adding an event listener, or setting a timer.

The useEffect hook takes two arguments:

- A function that contains the side effect you want to perform.
- An optional array of dependencies that determines when the effect should be re-run.

Here\'s an example:

```jsx
import React, { useState, useEffect } from 'react';

function ExampleComponent() {
    const [count, setCount] = useState(0);
    
    useEffect(() => {
      document.title = `You clicked ${count} times`;
    }, [count]);
    
    return (
        <div>
            <p>You clicked {count} times.</p>
            <button onClick={() => setCount(count + 1)}>Click me</button>
        </div>
    );
}
```

In this example, we\'re using the useEffect hook to update the document title based on the value of count. The first argument is a function that updates the document title, and the second argument is an array that contains the count variable. This means that the effect will re-run every time count changes.

If you omit the second argument, the effect will run on every re-render. If you pass an empty array, the effect will run only once, when the component mounts.

The `useEffect` hook is a powerful tool that allows you to manage side effects in your React components in a simple and declarative way.