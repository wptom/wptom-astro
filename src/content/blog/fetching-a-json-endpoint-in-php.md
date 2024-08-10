---
author: Tom
pubDatetime: 2022-12-24T15:22:00Z
title: Fetching a JSON endpoint in PHP
slug: fetching-a-json-endpoint-in-php
featured: false
draft: false
tags:
  - json
  - php
description: Learn how to fetch a JSON endpoint in PHP using cURL and decode the JSON response into an associative array.
---

This example uses the cURL library to execute an HTTP request to the specified URL. The response from the server is stored in the $response variable as a string. The json_decode function is then used to parse the JSON string and convert it into an associative array, which is stored in the $data variable.

You can then access the data in the $data array and use it as needed in your PHP script.

```php
<?php

// Set up the HTTP request
$url = 'https://example.com/api/endpoint';
$ch = curl_init($url);

// Set up the options for the HTTP request
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);

// Execute the HTTP request and store the response
$response = curl_exec($ch);

// Check for errors
if ($response === false) {
    // An error occurred
    $error = curl_error($ch);
    // Handle the error
}

// Close the HTTP request
curl_close($ch);

// Decode the JSON response
$data = json_decode($response, true);

// Use the data
```

Once you have fetched the JSON data and decoded it into an associative array, you can access the values in the array and display them as needed.

For example, if the JSON data contains a list of users, you can loop through the array and display the details of each user:

```php
<?php

// Set up the HTTP request and fetch the JSON data
// (This part is the same as in the previous example)

// Decode the JSON response
$data = json_decode($response, true);

// Check if the data is an array
if (is_array($data)) {
    // Loop through the array of users
    foreach ($data as $user) {
        // Display the user's name and email address
        echo "Name: {$user['name']}<br>";
        echo "Email: {$user['email']}<br><br>";
    }
}
```

This example assumes that the JSON data is an array of users, and each user has a name and email field. It loops through the array and displays the name and email address of each user.

Of course, you can customize this example to display the data in any way you like. You can use PHP functions like echo, print, or printf to output the data as HTML, text, or any other format. You can also use PHP\'s string interpolation syntax to insert the values from the array into the output string.