---
author: "Joseph LeRoy"
date: 2016-05-03
linktitle: "Visualizing Threats and Preventing Intrusions: Part 1"
nomenu:
  main:
    parent: tutorials
next: /tutorials/github-pages-blog
prev: /tutorials/automated-deployments
title: "Visualizing Threats and Preventing Intrusions: Part 1"
weight: 10
image: img/nidhogg.jpg
authorAvatar: img/petting-cat.jpg
---

For many years small and medium businesses would go unprotected and unaware of the dangers they face, leaving their web servers and private data susceptible to compromise. Sifting through thousands of lines worth of log data was often very tedious and difficult to accomplish without having a dedicated, well trained, technically apt staff to decipher event information. There was no proper way of incorporating log feeds from across multiple hosts into a central repository for event handling and interpretation. This disconnect would often hinder the security community’s resilience because the data was difficult to understand.

Incorporating a system (application stack) that consolidates log data and intelligence feeds into a clean, fast, and graphically represented format allows for an incredibly fast and lightweight SIEM (Security Information and Event Management) that fits into any organization’s needs. Correlating an organization’s live and historical log data and events with threat intelligence feeds can allow for an incredibly efficient method to deter threats or eradicating them if systems are already breached.

Many solutions are often too complex to integrate, difficult to scale, or are closed source and require a vendor installations and expensive contracts. They often fail to address the entire scope of the organization and are difficult to modify to match varying log data formats, events, etc. Why hasn’t it been solved before? That’s a highly debated question, however a few ideas come to mind. Security is often an afterthought when it comes to software development. The growth of user friendly open source software has been very stagnant for the past two decades. Software communities such as GitHub expanded the open source community by taking a holistic approach to social based open source revision control.

Utilizing a popular software stack, such as ELK (Elasticsearch, Logstash, Kibana), threat intelligence feeds, security hardening techniques, and network and host based intrusion detection systems, businesses can now make perfect sense of what’s happening on their network. Incorporating open source software to aggregate and interpret malicious activity in a scalable manner, from a few megabytes to several petabytes of log files and packet captures, on cloud based networks allows for massive cost savings, increased speed, and reliability over traditional in-house or co-located hosting. Each part of the businesses should be involved in the SIEM, and by developing specific dashboards through Kibana, the appropriate departments can quickly respond to events without having to wait for security teams to provide them with a report and instructions.

The next section of this research will introduce the ELK stack and how to install and configure it on Amazon AWS and Digital Ocean.