---
author: Tom
pubDatetime: 2022-12-25T15:22:00Z
title: Running a function once a day in PHP
slug: running-a-function-once-a-day-in-php
featured: false
draft: false
tags:
  - php
description: In this post, I will show you how to run a function once a day in PHP.
---

There are a few ways you can run a function once a day in PHP.

## 1. Use a CRON job

A CRON job is a time-based task scheduler in Unix-like operating systems. To set up a CRON job, you will need to have access to the command line and be able to edit the CRON table for your web server.

To set up a CRON job to run a PHP script once a day, you can use the following steps:

Open the CRON table for editing by running the following command:
`crontab -e`
Add the following line to the CRON table, replacing `\"path/to/script.php\"` with the actual path to your PHP script:
`0 0 * * * /usr/bin/php /path/to/script.php`

This line tells the CRON daemon to run the script at midnight (00:00) every day.

Save the CRON table and exit the editor. The CRON daemon will now run the script once a day at midnight.
## 2. Use a loop and a sleep function

For example, you can use the following code to run a function every 24 hours:
```php
while (true) {
// Run the function here
sleep(86400); // Sleep for 86400 seconds (24 hours)
}
```

This approach can be useful if you want to run the function on a specific schedule (e.g., every day at 3:00 AM) and you don\'t have access to a CRON daemon. However, keep in mind that this approach will keep the script running indefinitely, so you may want to add some additional logic to exit the loop after a certain number of iterations or at a specific time.