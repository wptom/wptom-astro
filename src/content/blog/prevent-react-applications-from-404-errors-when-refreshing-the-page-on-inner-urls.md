---
author: Tom
pubDatetime: 2023-02-27T15:22:00Z
title: Prevent React applications from 404 errors when refreshing the page on inner URLs
slug: prevent-react-applications-from-404-errors-when-refreshing-the-page-on-inner-urls
featured: false
draft: false
tags:
  - react
  - htaccess
description:  In this post, I will show you how to prevent React applications from 404 errors when refreshing the page on inner URLs.
---

This code is an Apache web server configuration file written in Apache\'s mod_rewrite syntax. It\'s commonly used in React applications to prevent 404 errors when refreshing the page on inner URLs.

```shell
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteBase /
RewriteRule ^index\\.html$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-l
RewriteRule . /index.html [L]
</IfModule>
```
In summary, this code tells Apache to rewrite all requests that aren\'t for an existing file, directory or symbolic link to the \"/index.html\" file. This allows the React application to handle the request and render the appropriate component, instead of returning a 404 error.