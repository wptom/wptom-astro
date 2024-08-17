---
author: Tom
pubDatetime: 2023-02-20T15:22:00Z
title: Fetch a JSON file in React using context
slug: fetch-a-json-file-in-react-using-context
featured: false
draft: false
tags:
  - react
  - json
description:  In this post, I will show you how to fetch a JSON file in React using context.
---

Assuming you have a `data.json` file in your project that contains an array of objects with some data:

```json
[
    {
        "id": 1,
        "name": "John",
        "age": 25
    },
    {
        "id": 2,
        "name": "Jane",
        "age": 30
    }
]
```


You can create a context to manage the data in your React app using the createContext function from the React library. Here\'s an example:

```jsx
import React, { createContext, useEffect, useState } from "react";

const DataContext = createContext([]);

const DataProvider = ({ children }) => {
    const [data, setData] = useState([]);
    
    useEffect(() => {
    // Fetch the data from the JSON file
    fetch("/data.json")
        .then((response) => response.json())
        .then((json) => setData(json));
    }, []);
    
    return <DataContext.Provider value={data}>{children}</DataContext.Provider>;
};

export { DataContext, DataProvider };
```

In the example above, we created a context called DataContext and a provider component called DataProvider. The DataProvider component fetches the data from the `data.json` file using the fetch API and stores it in state using the useState hook. The DataContext.Provider component wraps its children and passes the data through context.

Now, you can use the DataContext context in any component that needs access to the data. Here\'s an example of how you can consume the context in a component:

```jsx
import React, { useContext } from "react";
import { DataContext } from "./DataContext";

const DataList = () => {
const data = useContext(DataContext);

return (
    <ul>
    {data && data.map((item) => (
        <li key={item.id}>
          {item.name}, {item.age}
        </li>
    ))}
    </ul>
  );
};

export default DataList;
```

In the example above, we imported the `DataContext` context and used the useContext hook to access the data stored in the context. We then mapped over the data and rendered a list of items.

Remember to wrap your app with the `DataProvider` component so that the context is available throughout your app:

```jsx
import React from "react";
import { DataProvider } from "./DataContext";
import DataList from "./DataList";

const App = () => {
    return (
        <DataProvider>
          <DataList />
        </DataProvider>
    );
};

export default App;
```