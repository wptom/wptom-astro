---
author: Tom
pubDatetime: 2023-01-15T15:22:00Z
title: Examples of share a WordPress post links
slug: examples-of-share-a-wordpress-post-links
featured: false
draft: false
tags:
  - wordpress
  - php
description:  In this post, I will show you how to share a WordPress post link using various methods.
---

Share buttons on a website are a powerful tool that can help increase visibility, social proof, engagement, brand awareness, lead generation and viral reach.

Social shares are considered a positive signal by search engines, and can help improve your website\'s search engine rankings.

## Facebook

Here is an example of how you can create a link to share a WordPress post using the post\'s permalink:
```php
<a href="https://www.facebook.com/sharer/sharer.php?u=<?php echo urlencode(get_permalink()); ?>">
    Share on Facebook
</a>
```

This code creates an `<a>` tag with a href attribute that points to the `sharer.php` file on Facebook\'s servers, and the u parameter is set to the permalink of the current post, encoded with `urlencode()` function.

On click, the link will redirect the user to the Facebook share dialog, with the post\'s permalink pre-populated as the URL to be shared.

Please note that this solution does not use the Facebook JavaScript SDK, so it does not require an App ID or login to Facebook. The user will be redirected to the Facebook website to share the link, and the share count will not be updated on your website.

Also, you can customize the text of the link to be displayed as per your requirement, and also you can use css to replace the default link with your custom icon.

## Twitter

You can create a link to share a WordPress post on Twitter using a similar approach as for Facebook. You can construct the URL using the post\'s permalink and append it to the Twitter share URL.

Here is an example of how you can create a link to share a WordPress post using the post\'s permalink:
```php
<a href="https://twitter.com/intent/tweet?url=<?php echo urlencode(get_permalink()); ?>">
    Share on Twitter
</a>
```

This code creates an `<a>` tag with a href attribute that points to Twitter\'s intent/tweet page, and the url parameter is set to the permalink of the current post, encoded with `urlencode()` function.

On click, the link will redirect the user to the Twitter share dialog, with the post\'s permalink pre-populated as the URL to be shared.

You can also pass additional parameters such as text (the text of the tweet) or hashtags (hashtags to be included in the tweet)
```php
<a href="https://twitter.com/intent/tweet?url=<?php echo urlencode(get_permalink()); ?>&text=<?php echo urlencode(get_the_title()); ?>&hashtags=example,wordpress">
    Share on Twitter
</a>
```

As before this solution does not use the Twitter JavaScript SDK, so it does not require an App ID or login to Twitter. The user will be redirected to the Twitter website to share the link, and the share count will not be updated on your website.

You can customize the text of the link and also use css to replace the default link with your custom icon.

## Linkedin
```php
<a href="https://www.linkedin.com/shareArticle?url=<?php echo urlencode(get_permalink()); ?>&title=<?php echo urlencode(get_the_title()); ?>">
Share on LinkedIn
</a>
```
## Pinterest
```php
<a href="https://pinterest.com/pin/create/button/?url=<?php echo urlencode(get_permalink()); ?>&media=<?php echo urlencode(get_the_post_thumbnail_url()); ?>&description=<?php echo urlencode(get_the_excerpt()); ?>">
Share on Pinterest
</a>
```
## WhatsApp
```php
<a href="whatsapp://send?text=<?php echo urlencode(get_permalink()); ?>">
Share on WhatsApp
</a>
```

Please note that for WhatsApp, it will open the WhatsApp app with the permalink pre-populated in the message field if the user has the app installed, otherwise it will open the web version of WhatsApp.

Similar to the previous examples, these solutions do not use the social networks JavaScript SDK, so they do not require an App ID or login to the networks. The user will be redirected to the social networks website to share the link, and the share count will not be updated on your website.

Please keep in mind to validate the data before passing it to the share function, to ensure that it\'s safe and not prone to any attacks.