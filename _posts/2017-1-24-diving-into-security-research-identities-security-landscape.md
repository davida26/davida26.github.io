---
layout: post
title: Diving into Security Research - Identities and Vulnerabilities
category: Security-Research
description: Defining identity abilities, security and the overall landscape.
---

## Defining Identity Abilities
Before digging into how things work. It is important to understand the identity abilities that are a foundation to why security standards have been created. We must first understand ourselves before moving forward.

- <strong>Privacy</strong> - this is one of the key topics discussed everywhere today. The majority of people see privacy as important to have but have limited knowledge of what it actually is. In general, privacy deals with protecting what you do within some space. No one sees what you do but they may know who you are. 

Examples:

- encrypted email between you and a friend. Only your friend and yourself can see this email.
- you have privacy in your home but people know you live there.  

2. <strong>Anonimity</strong> - Concealing who you are. Non-attribution to actions.

Example
- In countries where controls are high, individuals use anonimity to access resources otherwise out of reach. They protect their identity.

- <strong>Pseudo-anonimity</strong> - Concealing who you are but keeping an alias. 

Example
- You like posting on a forum but do not want people to know your real name. However, you want the attribution of the posts you create so you develop an alias.

## The Overall Security Landscape (good and bad actors)

## Assets Layer
At the core of the landscape is people and our things (assets). We may want to keep our information private (logins, emails, files, etc). 

Whatever floats your boat in terms of privacy, the core is the layer we control. We choose who we share this information with whether directly or indirectly. As you will see later on, security is only as good as its weakest link and in this case it is us, humans. 

## Security Layer
Outside the core lies our security. Basically everything trying to protect us from whatever is out there. These are generally used together to minimize risk. 

This layer includes:
- TOR
- VPNs
- JonDonym
- Opsec
- Encryption
- Two-Factor Authentication (2FA)
- Security Patches
- HTTP Filters
- Firewalls
- OpenPGP
- SSL/TLS
- HTTPS
- SSH

## Threat / Vulnerability Layer
This is all the fun things that encrypt our PCs without us knowing, take down databases, look through our webcams and make our days more fun. Within this layer are:

- Vishing
- Phishing (those rhyme!)
- Adware
- Spyware (on a roll here)
- Rootkits
- RATS
- Malware
- Mass Surveillance
- Regulating Encryption
- Exploit Kits
- Backdoors

## Attacker Layer
The actors that use the approaches defined in the threat layer above to get to our assets within our core layer. Always good to know and understand your opponent to minimize risk. 

> Hence that general is skilful in attack whose opponent does not know what to defend; and he is skilful in defence whose opponent does not know what to attack. - Sun Tzu

These include but not limited to:
- Rogue Entities
- Governments
- Hackers / Organized Groups 
- Colleagues
- Law Enforcement
- Ex-Partners (yes she may be coming for you electronically)

## Evaluating Risk
Generally risk is defined as:

```

Risk = (Vulnerabilities x Threats x Consequences)

```

You can view this as what happens when threats exploit vulnerabilities and the consequences they have on your information. You can make this more mathematical by thinking about it this way:

- I have a total of 2 computers in my office with 5 updates pending. I recently read about that there are 10 threats going around exploiting these vulnerabilities. I look at the updates and these are patches to fix them. However, I do not have time to run the updates because I am too busy working.

Now "I am too busy" is a common human escape goat for everything. So let's evaluate the risk here:

RISK = 5 (updates for vulnerabilties) x 10 (threats) x 2 (pcs down) = 100

I am not using any scales here but if you get both your work computers compromised, I would say this risk is very high. Even if it was half this value, don't you rather have 2 functioning computers?

Most people dont think so and this is why security flaws exist.

## Security is not just technology
There are hundreds of security companies, fancy gadgets and other things that are aimed at protecting you from unathorized users. But as the example above shows, all the security in the world won't help you if you don't take the right actions. Develop the correct process to carry our the actions and take initiative in understanding the overall landscape.














