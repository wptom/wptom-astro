---
author: Tom
pubDatetime: 2022-12-21T15:22:00Z
title: Get previous and next post in Wordpress
slug: get-previous-and-next-post-in-wordpress
featured: false
draft: false
tags:
  - wordpress
description: In this post, I will show you how to get the previous and next post in Wordpress.
---

WordPress provides a built-in function called `get_adjacent_post()` which can be used to retrieve the previous or next post in the same category as the current post. You can use this function inside a loop to exclude the current post from the loop.

Here's an example of how you can use this function to retrieve the next post in the same category as the current post:

```php
$next_post = get_adjacent_post(false, '', true);
if($next_post) {
// Display the next post
}
```

You can also use the `get_adjacent_post()` function to retrieve the previous post in the same category as the current post by setting the third parameter to false.

```php
$prev_post = get_adjacent_post(false, '', false);
if($prev_post) {
// Display the previous post
}
```

You can also use the `previous_post_link()` and `next_post_link()` functions to easily display links to the previous and next posts in the same category as the current post. These functions will automatically exclude the current post from the loop.

```php
if(get_previous_post_link()) {
// Display a link to the previous post
previous_post_link();
}

if(get_next_post_link()) {
// Display a link to the next post
next_post_link();
}
```