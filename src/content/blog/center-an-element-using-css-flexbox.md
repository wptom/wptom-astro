---
author: Tom
pubDatetime: 2022-12-22T15:22:00Z
title: Center an element using CSS Flexbox
slug: center-an-element-using-css-flexbox
featured: false
draft: false
tags:
  - css
description: Learn how to center an element using the CSS flexbox layout.
---

To center an element using the CSS flexbox layout, you can use the justify-content and align-items properties.

Here\'s an example of how to center a div element horizontally and vertically using the flexbox layout:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Then, you can apply the container class to the parent element of the element that you want to center.

Here\'s an example of how to use this in a HTML file:

```html
<div class="container">
  <div>I am centered!</div>
</div>
```

The justify-content property aligns the element horizontally, while the align-items property aligns the element vertically.

Note that the flexbox layout only works on elements that have the display property set to flex.