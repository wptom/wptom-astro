---
author: Tom
pubDatetime: 2023-03-08T15:22:00Z
title: How to make a closable menu in Astro build
slug: how-to-make-a-closable-menu-in-astro-build
featured: false
draft: false
tags:
  - astro
description:  In this post, I will show you how to make a closable menu in Astro build.
---

In this example, we have a menu that is initially hidden with the .`hidden` class. When the user clicks on the \"Menu\" button, the `toggleMenu` function is called, which toggles the `.hidden` class on the menu to show or hide it. The menu also has a \"Close\" button that calls the same function when clicked.

The rest of the code is just a basic layout with a header and main content area, and some styles to make everything look nice.

```astro
Astro
---
name: layout
---
<astro>
  <script>
    export function toggleMenu() {
      const menu = document.querySelector(".menu");
      menu.classList.toggle("hidden");
    }
  </script>

  <nav class="menu hidden">
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About Us</a></li>
      <li><a href="#">Contact Us</a></li>
    </ul>
    <button class="close" on:click={toggleMenu}>Close</button>
  </nav>

  <div class="wrapper">
    <header>
      <h1>My Website</h1>
      <button class="menu-button" on:click={toggleMenu}>Menu</button>
    </header>
    <main>
      <!-- Page content goes here -->
    </main>
  </div>
</astro>

<style>
  .hidden {
    display: none;
  }
  
  .wrapper {
    max-width: 800px;
    margin: 0 auto;
  }
  
  nav ul {
    list-style: none;
    padding: 0;
  }
  
  nav li {
    margin-bottom: 1rem;
  }
  
  .menu-button {
    display: block;
    margin-left: auto;
  }
</style>
```
