---
author: "Joseph LeRoy"
date: 2016-05-15
linktitle: "Visualizing Threats and Preventing Intrusions: Part 2"
nomenu:
  main:
    parent: tutorials
next: /tutorials/github-pages-blog
prev: /tutorials/automated-deployments
title: "Visualizing Threats and Preventing Intrusions: Part 2"
weight: 10
image: img/nidhogg.jpg
authorAvatar: img/petting-cat.jpg
---

Network intrusions are an incredibly common occurrence that happens just about every single second on high traffic web servers. With the increasing popularity of cloud based systems, the entire range of IP addresses owned by the provider are constantly scanned and checked for vulnerabilities and poor security configurations. This can be replicated by creating a new VPS (Virtual Private Server) instance on a cloud hosting provider, such as Digital Ocean or Amazon AWS. Within minutes, the authentication log file will begin to fill up with brute force attempts trying to access SSH (Secure Shell) using default usernames and passwords. If you’re concerned with protecting your assets, it would be wise to disable root logins and require a public and private key pair to prevent password guessing attempts, among many other security hardening techniques.

![](https://storage.googleapis.com/josephbleroy-images/images/2016/05/auth.png)
**The two IP addresses listed in the image above resolve to a China based internet      service provider.**


The SANS Institute defines intrusion detection as "the act of detecting actions that attempt to compromise the confidentiality, integrity or availability of a resource". There are three main categories to intrusion detection systems: network based, host based, and physical. This research focuses primarily on network and host based intrusion detection and log analysis using applications and services such as Bro, Tripwire, Fail2Ban, among several others.   

Some of the most popular countries where hacking groups and individuals originate are China, the United States, and Russia. China has roughly 721 million internet users compared to the United States which has 286 million users and Russia with 102 million. Coincidentally, these countries rank among the most wealthiest and fastest growing economies. The United States currently ranks as the wealthiest country with $48.734 trillion dollars and China in second with $17.254 trillion. However, Russia does not rank among the top three wealthiest countries, but is one of the fastest growing countries. Russia’s wealth grew by 253% from 2000 to 2015. The importance of this information is that the economic status of a country might play a certain role in what fuels hackers, who they target, and what industries they seek to compromise.

The next part of this series will provide details on ways to search your log files using the ELK Stack, primarily focusing on Elasticsearch.