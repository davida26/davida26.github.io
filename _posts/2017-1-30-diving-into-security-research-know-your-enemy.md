---
layout: post
title: Diving into Security Research 4 - Know Your Enemy
category: Security-Research
description: Exploring the security landscape of today. NORSE, Bugs and Vulnerabilities, Common Types of Malware.
---

<small>This is a continuation of my deep dive into [Security Research](https://www.curatedcode.com/topics-collection/#security-research).</small>

## The Security Landscape Today

Unlike in the past, many attackers today are not sitting behind their computers launching attacks manually - who has time for that right? Due to the increase in cheap server providers and more publicly available vulnerability software many have moved their efforts to the cloud. Attackers today can setup code relatively quickly (some dont even have to lift a finger if they are willing to pay) and cast a net to fish for vulnerable devices / a specific target. 

Once a vulnerable device is found, the attacker is likely to have a database of vulnerabilities that deliver the right attack to that device. As the device is compromised it becomes part of the net casting attacks and or data from the device is delivered to the attacker. Again, looking at the [Defense in Depth](/security-research/2017/01/29/diving-into-security-research-defense-zero-trust/) principle, having layers is important to minimize this risk. If one fails, your others layers are there to protect you.

## Looking at Attacks: NORSE

Norse is the world's largest threat intelligence network. They monitor a portion of the internet traffic through "honeypots" or vulnerable servers. Once one of their servers is compromised they allow the attacks to go through so they can see the effects/gather data. Many of their servers emulate devices such as:

- ATM Machines
- CCTVs
- Critical Infrastructure Systems
- Mobile Devices, etc

NORSE provides a security software and hardware to improve overall security and ROI on larger networks. I am not affiliated with them in any way but appreciate the time they took to create the map below - it's pretty cool:

[NORSE Attack Map](http://map.norsecorp.com/)

## Known and Unknown Bugs

Attacks occur when a vulnerability is found. Vulnerabilties (Security Bugs) can be found in:

- Operating Systems
- Firmware
- Applications: Word, Excel, etc
- Browsers
- Browser Extensions

<strong>Example</strong>
Your browser is outdated and a malicious website (or a compromised *good* website - happened to Forbes before) has malware that exploits this vulnerability. A website can detect the browser/OS version you are using so it is important to always stay up-to-date when you are prompted to update. Let's look at the diffences in these bugs now:

-<strong>Known bugs</strong> like in the example above, these are also called patches. As the name states patches fix a problem with the software. These are your usual software updates. It is important update in a timely manner to protect against exploits.

-<strong>Unknown bugs</strong> on the other hand, often referred as zero days, are more dangerous. These are exploits that have been found but no patches exist yet. These can exist in two states public OR private. Some zero days are found by malicious groups who keep these secret and use them or sell to the highest bidder. As you can see, these are more difficult to protect because you either have to fix it yourself (if you are the programmer that found it/read about it) or you have no idea it exists so risk is involved. 

Database for [Vulnerability Research](https://www.cvedetails.com/).

## Malware in Detail

Generally, you cannot protect against everything but having the right security practice in place can minimize risk. 
Malware is the category where all malicious software is contained. Common types of malware are:

1. Macro Virus - stealthly embedded in documents (Word, Excel) to perform actions in the background when the document is executed.
2. Stealth Virus - attacks operation system processes and prevent anti-virus programs/scans from alerting a user. These generally hide in files, boot sectors and or partitions to prevent detection.
3. Polymorphic Virus - a difficult to detect virus due to the fact that it creates copies of itself with some slight modification. Changes paths so deleting one doesn't necessarily delete all. 
4. Self-garbling Virus - changes its code to prevent an anti-virus from detecting based on predefines signatures. Similar to a polymorphic virus.
5. Bots &amp; Zombies - a group of compromised machines that perform tasks.
6. Worms - viruses that spread from one machine to another.
7. OS Rootkits - hide their existence completely from the operating system.
8. Firmware Rootkits - less likely than the others but research has shown these exist.
9. Key Loggers - viruses that store all keystrokes.
10. Trojan - hidden viruses in other programs.
11. Remote Access Tools (RATs) - allow an attacker to gain control of your computer.
12. Ransomware - takes control of pc and starts to encrypt pc files in the background. Once the system is encrypted a message is show to the user to pay a fee to decrypt the files. [Interesting Ransomware: Jigsaw](https://www.bleepingcomputer.com/news/security/jigsaw-ransomware-decrypted-will-delete-your-files-until-you-pay-the-ransom/)
13. Malvertisement - an online ad that is infected with a virus. [Rig Exploit Kit](https://blog.malwarebytes.com/cybercrime/exploits/2016/09/rig-exploit-kit-takes-on-large-malvertising-campaign/)
14. Drive-by Attack - a website that contains malware (the website may or may not know its been compromised)
15. Spyware - gathers information about its target and sends information to the attacker.
16. Adware - software that forces advertisement on you. Example: coolwebsearch. Hijacks your browser and sets itself as the default search engine. Routes traffic to other websites. 
17. Browser Hijacking - takes over your browser, exists in various forms like above.
18. Scareware - virus that exploits the human emotion of fear. An example can be the ransomware above called jigsaw.
19. Potentially Unwanted Programs (PUPs) - bundled in with software, always go through custom installation and remove the extras you do not need.

[Curated Malware Analysis List](https://github.com/rshipp/awesome-malware-analysis)





