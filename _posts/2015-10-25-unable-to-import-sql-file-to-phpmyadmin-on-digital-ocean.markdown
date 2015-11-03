---
layout: post
title: Unable to Import SQL File to phpMyAdmin
---

Problem: Unable to Import SQL File to phpMyAdmin on Ubuntu Server Hosted on Digital Ocean

Fix: We need to change a few limitations on the server to upload our file. phpMyAdmin will tell us which to check, we just need to find those resources on the server.

Error Resource: [Found Here.](http://docs.phpmyadmin.net/en/latest/faq.html#faq1-16)

Sample Error:
(/assets/UnableToImportSQL.png)

## Lets Get Started

So the main problem here is that the server has been either modified with lower limits (some hosting companies do this) or the defaults (as in my case using Digital Ocean) are too low. Whatever the case may be, its an easy fix.

# The Main Culprits

1. upload_max_filesize
2. memory_limit
3. post_max_size

These are located in the configuration file: *php.ini*

#Finding the file

There are many ways to search for the file. One quick way is to search your server for php.ini or any file is using the following:

{% highlight bash %}
sudo find / -name php.ini
{% endhighlight %}

This approach is quick and will find the file you need but will also reveal [several other php.ini] (

http://askubuntu.com/questions/356968/find-the-correct-php-ini-file) files. The one you want is the one for apache. Located here:

{% highlight bash %}

/etc/php5/apache2/php.ini

{% endhighlight %}

So now you found your file. Now we need to edit a few areas within this file to increase our limits and upload our DB file.

#General Formula

post_max_size and memory_limit > upload_max_filesize

This is suggested so that if you have a very large file, you have enough memory and post data to handle it. More on the php.ini directives can be found [here](http://php.net/manual/en/ini.core.php)

Now in my case the defaults were set to:

1. post_max_size: 128M
2. memory_limit: 8M
3. upload_max_filesize: 2M

Everything looked ok until I noticed that my file was 7.5M. So ofcourse, this was way over my max_upload_filesize. 

#Editing the file

{% highlight bash %} 

Sudo nano /etc/php5/apache2/php.ini //open the file for editing

{% endhighlight %}

Use control + W (^W) to find the line in the file: *upload_max_filesize*

Once I found it, I edited it to 10M and updated the memory_limit to 12M just to comply with the general formula above.

lo and behold, it resolved the issue.

(/assets/SuccesfulImport.png)

And that's it, simple and to the point. Easy way to fix a php.ini when you are unable to import a DB file. 

Using Linux Ubuntu on Digital Ocean.



