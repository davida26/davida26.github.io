---
layout: post
title: Diving into Security Research 3 - Defense in Depth
category: Security-Research
description: A brief overview of the Defense in Depth principle and the Zero Trust Security Model
---

## Defense in Depth

Defense in Depth is a principle in security that takes the approach of providing security in layers. The layers are:

### Prevent > Detect > Recover		

- Prevention: protect files, network, etc to prevent access to confidential information.
- Detection: set up monitoring of files/hardware to get notified when it has been breached.
- Recover: if all else fails, a backup is available to restore information.

The approach is derived from a military principle where it is more difficult for an enemy to defeat a complex, multi-layered defense than a single point. Defence in Depth is useful to minimize the probability that a compromised system is unrecoverable.

[Sans Institute Reading Room: Defense in Depth](https://www.sans.org/reading-room/whitepapers/basics/defense-in-depth-525)

## Zero Trust Model

The Zero Trust Model basically states that you should trust no one and evaluate everything. It is designed to mitigate risk by first analyzing what is important.

<strong>Example:</strong>

Using some cloud storage service like Dropbox/Google/OneDrive to store your files. Zero Trust Model would tell you that you can't trust the servers that information is stored in. No matter how secure they are there is always a risk. There could be a breach or someone within those companies could access your files. So what do you do?

<strong>Possible Solution #1</strong> - encrypt the files. This provides an additional layer of security outside whatever those companies offer. However, it doesn't fully solve the problem of protecting the files. What happens if all the encrypted files are deleted?

<strong>Possible Solution #2</strong> - backup the files. If all the encrypted files happen to be deleted, you have a backup. Using both solutions simultaneously would provide a more robust approach to protecting your data.

Zero Trust, Evaluate Everything. 

Great reads about research conducted on The Zero Trust Model:

[Developing a Framework to Improve Critical Infratruscture Cybersecurity](http://csrc.nist.gov/cyberframework/rfi_comments/040813_forrester_research.pdf)

[Google Adopts Zero Trust Model: BeyondCorp](https://research.google.com/pubs/pub43231.html)



