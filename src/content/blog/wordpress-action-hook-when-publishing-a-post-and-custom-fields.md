---
author: Tom
pubDatetime: 2022-12-28T15:22:00Z
title: WordPress action hook when publishing a post and custom fields
slug: wordpress-action-hook-when-publishing-a-post-and-custom-fields
featured: false
draft: false
tags:
  - wordpress
description:  In this post, I will show you how to use a WordPress action hook when publishing a post and how to save custom fields when a post is published.
---

To create a WordPress hook when publishing a post, you can use the publish_post action hook. This hook is triggered whenever a post is published, or if a post is updated and its status is changed to \"published.\"

Here\'s an example of how you can use this hook to create a custom function that runs whenever a post is published:
```php
function custom_function_on_publish( $post_ID ) {
    // your code here
}
add_action( 'publish_post', 'custom_function_on_publish' );
```
In this example, the custom_function_on_publish function will be executed whenever a post is published. The $post_ID parameter is passed to the function, which contains the ID of the post being published.

You can use this hook to perform any action you\'d like, such as sending an email notification, updating a custom field, or anything else you can imagine. Just make sure to add your code inside the custom_function_on_publish function.

Using publish_post action hook to update a custom field when a post is published
```php
function update_custom_field_on_publish( $post_ID ) {
    // get the value of the custom field
    $custom_field_value = get_post_meta( $post_ID, 'custom_field_key', true );
    
    // update the custom field with a new value
    update_post_meta( $post_ID, 'custom_field_key', 'new_value' );
}
add_action( 'publish_post', 'update_custom_field_on_publish' );
```
In this example, the update_custom_field_on_publish function will be executed whenever a post is published. The function uses the get_post_meta function to retrieve the current value of the custom field with the key custom_field_key, and then uses the update_post_meta function to update the custom field with a new value.

You can modify this code to suit your specific needs. For example, you might want to update the custom field with a value from a form field, or retrieve the value from an external API.

Creating custom field

To create a custom field in WordPress, you can use the add_post_meta function. This function allows you to add a custom field to a post, page, or custom post type.

Here\'s an example of how you can use the add_post_meta function to create a custom field when a post is published:
```php
function create_custom_field_on_publish( $post_ID ) {
    // check if the custom field already exists
    $custom_field_value = get_post_meta( $post_ID, 'custom_field_key', true );
    if ( empty( $custom_field_value ) ) {
    // if the custom field doesn't exist, add it
        add_post_meta( $post_ID, 'custom_field_key', 'custom_field_value' );
    }
}
add_action( 'publish_post', 'create_custom_field_on_publish' );
```

In this example, the create_custom_field_on_publish function is executed whenever a post is published. The function uses the get_post_meta function to check if the custom field with the key custom_field_key already exists for the post. If it doesn\'t exist, the function uses the add_post_meta function to add the custom field to the post.