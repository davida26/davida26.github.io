---
layout: post
title: Working with Composer
---

The web ecosystem of today is revolutionary. Everyday we are creating new tools, frameworks, standards and engineering new ideas to push further. This weekend I decided to take up exploring a PHP framework called Laravel. Coming from a RoR background, I was familiar with the MVC architecture behind it. It was also fun to explore and evaluate its potential because it took me back to my early days. Days where I was working for a local web company building WordPress powered sites. Overall, I figured laravel would be a good fit to re-tinker with PHP and MVC.

Along the way, I picked up a few PHP tools that in my early days as a developer, I did not have. 

## Enter Composer

Composer is a dependancy manager for PHP. If you are new to PHP, this basically helps you install different open source packages to use in your projects. So if you don't want to re-invent the wheel and you want take advantage of large community of developers, this is the way to go.

## Installing Composer

Using and installing composer has been super easy. Almost no learning curve and maximum efficiency with regards to prioritizing your development time to features you actually need to build.

To get started with composer simply go to [getcomposer.org] (https://getcomposer.org/) and hit download. You will be presented with different options depending on your system. In my case, I am on OSX so i ran the following command:

{{% highlight console %}}

curl -sS https://getcomposer.org/installer | php

{{% highlightend %}}

This will install composer and get all the required files for you. When it completes you should have something like this:

{{% highlight console %}}

➜  ~  curl -sS https://getcomposer.org/installer | php
#!/usr/bin/env php
All settings correct for using Composer
Downloading...


Composer successfully installed to: /Users/David/composer.phar
Use it: php composer.phar

{{% highlightend %}}

Notice the last line tells you how to use it. This of course is not very practical because this would mean that everytime I want to use composer I would have to type *composer.phar*

## The Fix

Fix is simple. All you need to do is move the *composer.phar* to your your local *bin* directory. Notice that we are moving it there into its own directory called composer.

{{% highlight console %}}

mv composer.phar /usr/local/bin/composer

{{% endhighlight %}}

And bingo. You are all set to get started with composer. So lets test it.

## Testing our installation

Let's start testing composer to make sure our install works. In your CLI type in the following:

{{% highlight console %}}

composer

{{% highlight end %}}

this will run composer and give you all its option. If you see the list you are good to go!

## Using Composer

So of course Composer is great if you use it to add what you need for your projects. Going back to the above, my whole goal here was to get Composer so I can install laravel and manage dependancies easier.

To use composer to install Laravel I used the following command:

{{ % highlight console %}}

composer create-project laravel/laravel lavarel-app

{{% highlightend %}}

This will run through all the dependancies Laraval needs and install them as well as Laravel itself.

You may be wondering how I knew what to type above. Well, I didn't actually. However, what I did know was the following:

1. The *composer* command - just like all other tools, you need to call the tool.
2. That I needed to create a project using composer and seeing the docs for composer: *create-project* was exactly what I needed.
3. I needed to install Laravel. So as mentioned above, I went to (packagist.org) [https://packagist.org/search/?q=laravel] and did a search for Laravel. Above the title, it tells you the require name.

*laravel/laravel* the syntax here is the VendorName/PackageName which is what composer needs.

4. I wanted to store this new app in a directory called laravel-app. So the last section creates that for me.

## More about Composer

Of course there is much more you can do with composer. I highly encourage you to read their documemtation. It is pretty robust and provides everything you need to extend your composer knowledge.



 