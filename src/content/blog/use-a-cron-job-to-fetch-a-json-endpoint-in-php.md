---
author: Tom
pubDatetime: 2023-01-07T15:22:00Z
title: Use a cron job to fetch a JSON endpoint in PHP
slug: use-a-cron-job-to-fetch-a-json-endpoint-in-php
featured: false
draft: false
tags:
  - css
description:  In this post, I will show you how to create a national flag by using CSS gradient.
---

A cron job is a scheduled task that runs automatically at specified intervals on a Unix-based operating system. The name \"cron\" comes from the Greek word \"chronos\", which means \"time\". Cron is a time-based job scheduler in Unix-like operating systems. Users that set up and maintain software environments use cron to schedule jobs (commands or scripts) to run automatically at a specified time/date. These jobs are commonly refered as \"cron jobs\".

Cron reads the configuration file called crontab (cron tables) for predefined commands and scripts. The commands to be executed on a specified time are defined in this file. Cron then wakes up every minute, examining all stored crontabs, checking each command to see if it should be run in the current minute.

First, you will need to set up a cron job on your server. This is usually done through the command line by editing the crontab file. To do this, open a terminal window and enter the following command:
crontab -e
This will open the crontab file in a text editor. Add the following line to the file to schedule the cron job to run every hour:
`0 * * * * /usr/bin/php /path/to/fetch_json.php`
Next, create a PHP script called \"fetch_json.php\" in the specified path. This script will contain the code to fetch the JSON endpoint.
In the PHP script, use the file_get_contents function to fetch the JSON data from the endpoint URL:
```php
$json = file_get_contents('http://example.com/endpoint.json');
```
The file_get_contents function returns a string containing the JSON data. To parse the JSON data into a PHP array, use the json_decode function:
```php
$data = json_decode($json, true);
```
Now you can access the data in the array as needed. For example, you could loop through the array and perform some action on each element:
```php
foreach ($data as $item) {
// do something with $item
}
```
When you are finished, save the PHP script and exit the text editor. The cron job will now run every hour and fetch the JSON data from the endpoint.
Additional examples of CRON job schedules that you can use in your crontab file
To run the job every minute: `* * * * * /path/to/command`
To run the job every 15 minutes: `*/15 * * * * /path/to/command`
To run the job every hour at 30 minutes past the hour: `30 * * * * /path/to/command`
To run the job every day at 5:00 AM: `0 5 * * * /path/to/command`
To run the job every Monday at 5:00 AM: `0 5 * * 1 /path/to/command`
To run the job every 1st of the month at 5:00 AM: `0 5 1 * * /path/to/command`

Remember that the cron job schedule consists of six fields: minutes (0-59), hours (0-23), day of the month (1-31), month (1-12), day of the week (0-6, with 0 being Sunday), and the command to be run. You can use the asterisk (*) to specify that the job should be run for all possible values of the field.