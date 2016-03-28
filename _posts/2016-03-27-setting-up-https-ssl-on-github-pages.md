---
layout: post
title: Setting up HTTPS (SSL) on GitHub Pages through CloudFlare
category: Security
description: Learn how to set up GitHub Pages on HTTPS (SSL/TLS) through CloudFlare. Get a FREE SSL with CloudFlare and add HTTPS to your site.
---

### A brief introduction to HTTPS and why use it

HTTPS is the *secured* version of HTTP (Hypertext Transport Protocol). HTTP is the protocol used to define how messages are sent or received over Internet. So why use HTTPS?  

1. It offers a higher level of security because these messages are sent over SSL/TLS. In other words, a nifty third-party that could once have intercepted the messages by hijacking a connection will now have some difficulty. 
2. Good for search engine rankings as [Google has mentioned](https://webmasters.googleblog.com/2014/08/https-as-ranking-signal.html).
3. Allows your visitors to see that someone actually cares about protecting information. Notice the green lock at the top of this site.

[Learn More about the difference between HTTPS/SSL/TLS.](http://security.stackexchange.com/questions/5126/whats-the-difference-between-ssl-tls-and-https)

### Adding SSL to your GitHub Page

This year, I set out to update my blog and make it compliant with Google's Best Practices. As mentioned above, HTTPS pages are ranked better so let's get to it.


#### 1. Adding a custom domain name to your GitHub Page

By default creating a site on github pages will give you something like *davida26.github.io*. While that is cool to start out with, you probably want your own domain to make it more about you. To make this happen, first you need to create file called *CNAME* and add your domain. In my case:

```
www.curatedcode.com
curatedcode.com
```

Once the *CNAME* file has been added to the root of your project you need to go to your domain registrar and make some DNS changes. In my case, I am using Google Domains but the approach is similar for others.

![Google Domains, GitHub Pages]({{site.url}}/assets/google-domains-github-pages.png)

Once that is done you, visit your new domain to make sure everything is loading correctly. 

#### 2. Get an SSL, you can get one FREE at [CloudFlare](https://www.cloudflare.com/) 

We are at the dawn of a new age where the once expensive SSL's are now attainable for personal/small projects.  So sign up and add your domain. CloudFlare will begin looking up your DNS Records and populate all the information it needs. 

**Note:** I am assuming that you already had your site loaded and working under a domain. If you did not then you might want to do that first aka Step 1.  

#### 3. Make sure your config.yml file is ready for https and any relevant assets

We want to serve everything on our site through https. In my *_config.yml* file I had originally set the url to http://. If you are in the same boat update it now.

```
url:              https://www.curatedcode.com
```

I also had Google fonts in my header set to http://. Change it to:

``` html
 <link rel="stylesheet" href="//fonts.googleapis.com/css?family=Open+Sans:400">
```

Google fonts should use href="//" so the browser automatically determines the right http version.

#### 4. Setup the new CloudFlare DNS Servers

CloudFlare will provide you these. Just add them to your Name Servers section like so:

![DNS Settings for Github Pages]({{ site.url }}/assets/google-dns-servers-github-pages.png)

#### 5. Configure CloudFlare to serve HTTPS

Since you made it this far, you are ahead of the curve. This next part is easy, just update the following tabs in CloudFlare:

<strong>Crypto</strong> - set to flexible, this option does not require an SSL to be added at the server level. Given that this is for a simple blog site hosted on GitHub Pages, this works. 

**Note:** This option should not be used on larger, information sensitive sites. There is a space here (between the origin server and cloudflare) that is not secured and can be exploited. However, at the time of writing this is easiest solution to add https if you are using GitHub Pages to host your site. There is a [great article](https://www.agwa.name/blog/post/cloudflare_ssl_added_and_removed_here) by Andrew Ayer that talks more about this security issue.

<strong>Page Rules</strong> - set a forwarding rule to force https in all your urls. I created two rules here, one for https to be enforced. The other to redirect http to https.

![Enforce HTTPS GitHub Pages]({{ site.url }}/assets/CloudFlare-Forwarding.png)

#### 6. Grab yourself a beer

Congratulations! You have now added https to your site.


