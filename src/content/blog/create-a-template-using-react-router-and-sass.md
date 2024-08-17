---
author: Tom
pubDatetime: 2023-01-29T15:22:00Z
title: Create a template using React router and SASS
slug: create-a-template-using-react-router-and-sass
featured: false
draft: false
tags:
  - react
description:  In this post, I will show you how to create a template using React router and SASS.
---

1. Start by creating a new React project using CRA by running the command `npx create-react-app my-app`.
2. Next, install react-router-dom by running the command `npm install react-router-dom`.
3. In the src folder, create three new files: Home.js, About.js, and Contact.js. These will be the components for your three pages.
4. In the src folder, create a new file Routes.js. This file will be used to define your routes.
   5. In Routes.js import React from \'react\' and {BrowserRouter as Router, Route} from \'react-router-dom\'.
6. Define three Routes, one for each of the pages you created in step 3.

1. In App.js, import the Routes component and render it inside the return statement of the App component.
2. To use Sass in your React project, install the node-sass package by running the command npm install node-sass.
3. In your src folder, create a new folder called sass. Inside this folder, create a new file called main.scss.
4. In each of your page components, you can import the main.scss file and use the styles defined in it.
5. To run the app, use `npm start command`

Here is an example of the full code for each of the files described above:

`src/Routes.js`

```javascript
import React from 'react'
import { BrowserRouter as Router, Route } from 'react-router-dom'
import Home from './Home'
import About from './About'
import Contact from './Contact'

function Routes() {
    return (
        <Router>
        <Route path="/" component={Home} exact />
        <Route path="/about" component={About} />
        <Route path="/contact" component={Contact} />
        </Router>
    )
}

export default Routes
```

`src/App.js`

```javascript
import React from 'react'
import Routes from './Routes'

function App() {
    return (
        <div>
        <Routes />
        </div>
    )
}

export default App
```

`src/Home.js`

```javascript
import React from 'react'
import '../sass/main.scss'

function Home() {
    return (
        <div className="container">
        <h1>Home Page</h1>
        </div>
    )
}

export default Home
```

`src/About.js`

```javascript
import React from 'react'
import '../sass/main.scss'

function About() {
    return (
        <div className="container">
        <h1>About Page</h1>
        </div>
    )
}

export default About
```

`src/Contact.js`

```javascript
import React from 'react'
import '../sass/main.scss'

function Contact() {
    return (
        <div className="container">
        <h1>Contact Page</h1>
        </div>
    )
}

export default Contact
```

`src/sass/main.scss`

```scss
.container {
    text-align: center;
}
```

Please note that this is a basic example and you may want to add more functionality and styles to your components as needed. Also, Make sure that you\'ve installed the necessary packages react-router-dom and node-sass.