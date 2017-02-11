---
layout: post
title: Diving into Security Research 5 - Understanding Phishing Attacks
category: Security-Research
description: Understanding phishing attacks. What is phishing? How do these attacks occur? Preventing phishing attacks.
---

## What is phishing?
Phishing is a fraudulent attempt to steal user information through the use of email, calls, SMS or websites. Phishing attacks are often masked and can look as if they are coming from a reputable source. These attacks are faily easy to set-up, require minimal resources and are highly successful due to their masking techniques.

Phishing is an example of social engineering were simple techniques are used to deceive users.

## Phishing Explained
Phishing is relatively easy to explain, difficult to put into practice and still a risk no matter how much security an organization may have. Research shows that approximately 30% of organizations experience security issues due to Phishing Attacks. This number may be significantly higher if we account for smaller business entities who are not part of the reported metrics. 

Let's look at examples.

<strong>Example 1 - Phishing Call</strong>

This is one of my favorite examples. It also brings back to my mind the principle of Defense in Depth. It is always important to have different layers to protect ourselves. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/HrCy050uaEU" frameborder="0" allowfullscreen></iframe>

<strong>Example 2 - Phishing Emails / Websites</strong>

We see these all the time and they get better each year. Here is one I have seen that brings a few things together:

The Dropbox Scam - How it Works
1. They trick you by [spoofing](https://en.wikipedia.org/wiki/Email_spoofing) the email address. So the email can come from say support@dropbox.com. If your spam filter didn't pick it up, you are likely to fall for this. (Gmail and a few others do block this - most of the time)
2. The email itself has a nice HTML layout with the right logo, colors and call to action button. Often, it tells you that you need to update your password or login to review your account. They want you to have some urgency so its common for an alert-like email to be sent.
3. If you click on this email you may be redirected to a page that looks exactly like the Dropbox website. So you enter your username and password.
4. The page then redirects you to the real dropbox.com website. Where you see the login form again. So you enter your details again and login normally. It worked, you have no alerts here so you close it off and think nothing of it.

Now if you caught on already, *Step 3* took you to a website that isn't the real Dropbox. If you are not tech savvy or they catch you at a time of day where you are busy and unfocused you fell for the scam. They got your email and password now. They can do as they please with your Dropbox account. From experience I've seen a nice piece of ransomware spread from dropbox to dropbox. What a joy to decrypt multiple PCs!

Now for those that are a little more cautious or received some training from your organization, you may have glanced at the URL and saw this when you landed at the dropbox page:

'''
www.dropbox.secured-email-12.com
'''

Organizations provide training to their employees to spot fake emails/websites. Most of the time employees just briefly glance at the first part to identify if it matches something they were trained to look for. Here is sample logic they use in situations like this:

1. Does the email sender from say dropbox? YES
2. Does it have the right logo?  YES
3. Does the email look safe? YES 
4. Does the website resemble dropbox? YES
5. Does it look secured? Well the address bar says "secured email" and I just clicked on an email. OK I am good to proceed.

And before you know it, all the training went down the drain. It was a nicely made email, identical to the real one. The email was spoofed or came from something that had the word dropbox in it. The website was identical and your employee had no idea this even happened since they were able to actually login (after it quietly redirected them, people expect a page to refresh when you click a login button).

<strong>Example 3 - Email From Your Coworker/Friend</strong>

Now you know that emails can be spoofed (sent from someone's email address that you know but it's not actually that person). Here is an example of how this tactic is used when company emails or personal address books are compromised.

1. Bill sends me an email frequently on status updates. I read them and reply back.
2. One day the emails are compromised and an attacker has Bill's email. He uses his computer to send an email to all of Bill's contacts.
3. As I am used to looking at emails from Bill, I notice there is a link he sent me to check out in his last email. I click on it.

Once again the attacker has won. We didnt take the time to look at the link or it may have been masked as "Click Here".

<strong>Example 4 - SMS</strong>

Calls and Emails are not the only methods of falling for a phishing attack. Nowadays, we are getting phishing via SMS. 

1. You get a text message from 242-2 or something like that.
2. The message is a text from Bank of America or something similar, Alerting you about your "account"
3. The message has a link to view it.
4. Message link is to a website that looks like your bank. 

If you are on mobile and happen to have that bank, you may be tempted to click on it. Falling for this one is easier than you think (less common though) since you are likely on the go. The behavior here is: mobile users like to get things done fast. Security goes out the drain. 


## Preventing Phishing Attacks

Phishing attacks as mentioned are a type of social engineering. The best way to prevent them is to stay vigilant, have a defense in depth policy established and if you dont know, ask someone.

In the business world, the best way to avoid these scams is to train people and establish a process where if it looks weird or have no idea your "account was changed", send it to the IT department or if you dont have one, go through the list of checks to validate it. Never assume.

### How to Validate a Phishing Email

1. Look at the sender - if its from dropbox.com.secured-email-12.com it's not the same as dropbox.com.
2. Look at the email contents - is this something dropbox would send, would Bill share this with you? Is the email in proper english? 
3. Check all links in the email - if there is a nice blue button right in the middle, first right click and copy the link address. Paste it somewhere that you can see its path. 
4. If it all checks out but you still have some suspicions, call the person. Remember we can still call people nowadays or IM them. Make sure to ask they sent you XYZ email.
5. If you cant reach them, ask your IT Department or wait for the person to respond to you.

### Common Link Example Types in Phishing Emails

<strong>Subdomains / Different Domain Names</strong>

- http://www.google.com.secured-123456.com/login - this is not the real Google.com
- http://www.secured-123456/google.com/login

<strong>Homograph - slight change in domain</strong>
- http://www.drob8ox.com - little change of character, easy to miss
- http://www.g00gle.com

<strong>Hidden URLS - links with text shown</strong>
- Click Here - the actual link is hidden in html

'''html
<a href="http://www.google.com.badDomain.com">Click Here</a>
'''

- Rich HTML (emails with buttons or images)

### Top 10 List of Scams Resource

Here is a lisk from Consumer Fraud Reporting about the current top 10 scams:

[http://www.consumerfraudreporting.org/current_top_10_scam_list.php](http://www.consumerfraudreporting.org/current_top_10_scam_list.php)





