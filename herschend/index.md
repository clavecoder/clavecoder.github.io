<!-- markdownlint-disable first-line-h1  -->
<!--
 cSpell:ignore herschend herschend's xers snapchat pokéman united's
 cSpell:ignore tibco corba dcom msmq brokerless amqp mqtt rtos
-->

# Herschend Director of Enterprise Web Architecture Position Analysis


**Kenneth Brubaker<br>
2017-02-19**

<!-- markdownlint-disable ul-style -->

> ## Table Of Contents
> - [Executive Summary](#executive-summary)
> - [Caveat](#caveat)
> - [Introduction](#introduction)
> - [Distributed Systems](#distributed-systems)

<!-- markdownlint-enable ul-style -->

## Executive Summary

- Introduction
  - Author shares misgivings about preparing an analysis with so little
    information
  - A new software architecture is needed to capture the opportunities
    provided and challenges posed by the next decade
  - A Director of Enterprise Web Applications provides hub around which
    to develop and deliver that architecture
- Distributed systems
  - A history of distributed systems is discussed
  - Current distributed systems technologies are discussed
  - A formal product review process is essential to determine the
    appropriate technology for Herschend. The approach is discussed
    elsewhere in the document

## Caveat

I've been asked by Jon Dilly at **iStaff** to provide an analysis of the
Director of Enterprise Web Architecture position at Herschend. I don't
feel very comfortable providing analysis with only a few hours worth of
conversation but with the caveat that my assessments may drastically
change as I learn more about Herschend and it's business, I will proceed
with what I feel may be a reasonable approach to the position.

## Introduction

### Entertainment in the 2020's

As we prepare to enter the third decade of the 21st century, Herschend
is poised to transform it's software architecture to better meet the
opportunities and challenges of a new connected reality.

Among Herschend's key demographics are youth and young adults with
children. In the 2020's, Millennials, who have grown up on the web
and Playstation, expect a connected entertainment experience. Even more,
the youth, children of Gen Xers such as myself, have come of age
immersed in world of ubiquitous connectivity through mobility—the world
of Instagram, Snapchat, and Pokéman Go. Both Millennials and Gen Xers
consider technology to be their most defining characteristic
([\[Pew14\]][Pew14] Figure 3.2). Catering to these demographics
require an increasingly connected entertainment experience.

Finally, immersive interaction provides heightened engagement with the
customer and guests that will provide increased sales opportunities and
greater customer satisfaction.

### The age of connected things

A similar trend is occurring in the world of machines and devices. With
Wi-Fi modules to be had for as little as $1 [\[GBMod\]][GBMod] no longer
should we consider machinery as merely mechanical or electrical systems.
Moreover, the prospect of connected devices provides unprecedented
opportunity for preventing and mitigating downtime of entertainment
and amusement center rides and providing more opportunities to delight
the guest.

### A new connected architecture

To meet the opportunities and challenges that Herschend faces in the
coming decade, a new distributed and connected architecture must be
envisioned and enacted using technologies and practices to which Herschend
has not been used in the past. A Director of Enterprise Web Architecture
provides a nexus around which to plan, construct, and deliver
distributed and connected software systems to meet the needs of the 2020's

## Distributed Systems

### A short history of distributed systems

The concept of distributed systems is not new. Traditional systems
involved substantial ongoing investment into a vendor's messaging or
Enterprise Service Bus (ESB) platform. The author has interacted
with many such systems over the years, including United's Galileo computer
reservation system, TIBCO, webMethods, IBM WebSphere ESB, MSMQ, and BizTalk.
This approach could be summed up as *Dumb Endpoints/Smart Pipes*.

Another approach envisions a more decoupled approach of independent peer
services conversing over a shared protocol, often using a common message
broker. The author worked for one of the founding members of one of
these efforts, CORBA. Other such technologies that the author has
interacted with include IPX, TCP/IP (the internet), DCOM, XML Web Services,
Windows Communication Foundation (WCF), an implementation of the WS-*
series of standards, and finally REST, the communications protocol for
HTTP (the web). These application and transport layer protocols can be
characterized as *Smart Endpoints/Dumb Pipes*.

While in the past debates and large sums of money have been bandied
about over the issue of how to best connect distributed systems, much of
the industry has settled down to using REST for customer facing systems
and combination of more specialized messaging systems internally. These
include lightweight brokerless technologies such as ZeroMQ, and brokered
messaging protocols. Major players include Kafka, RabbitMQ, and the
Advanced Message Queuing Protocol (AMQP) compliant ActiveMQ. For device
networks, i.e., Internet of Things (IoT), MQTT often used unless
real-time operating system (RTOS) is required. For logging and monitoring
communication, Kafka and StatsD are used along with a plethora of
proprietary monitoring protocols and services.

As cloud based providers have exploded in size and number, the balance
of power has shifted away from the gridiron software vendors to cloud
software providers creating and sharing their own protocols and
implementation. Most of the technologies just mentioned fall into this
category. Since software development at scale has democratized with the
advent of cloud hosting, software providers have looked for ways to
increase software delivery velocity.

To facilitate independent deployment of system capabilities,
increasingly have turned away from the *smart pipes* approach which
enforces a high degree of coupling between the components and especially
with the central system. Instead, they have turned to a
*smart endpoints* approach employing teams of developers delivering
independent systems within the organization that interact over standard
protocols, most especially REST, which can be considered the universal protocol.

### Distributed systems choices

That Herschend sees the need to adopt distributed computing principals
has already been expressed by several staff members. While, perhaps not
the most critical technology choice to be made for short term success,
it is nonetheless vital to the long term competitive advantage for
Herschend with respect to their systems integration capability. Equally
important a misstep in choice of technology or execution could be very
costly. It is, therefore, very important that a detailed investigation
and formal product review be executed early in the planning stage of the
initial project. The method of the formal product review is discussed
elsewhere in this document.

---

<dl>
  <dt>GBMod</dt>
  <dd>
    <a href="http://www.gearbest.com/transmitters-receivers-module/pp_218375.html?currency=USD&vip=760186&gclid=CjwKEAiAoaXFBRCNhautiPvnqzoSJABzHd6hYmyPQi13nlt5vRc7fABB9Pm2dAl1qRAbDFvsmDx2UxoCh7Dw_wcB">
      NRF24L01+ Enhanced Wireless Module  -  BLACK 1</a><br/>
    GearBest, <i>Accessed 2017-02-17</i>
  </dd>
  <dt>Pew14</dt>
  <dd>
    <a href="http://www.pewresearch.org/fact-tank/2014/06/05/generation-x-americas-neglected-middle-child/">
      Generation X: America’s neglected ‘middle child’</a><br/>
    Pew Research Center, 2014-06-14
  </dd>
</dl>

[GBMod]: http://www.gearbest.com/transmitters-receivers-module/pp_218375.html?currency=USD&vip=760186&gclid=CjwKEAiAoaXFBRCNhautiPvnqzoSJABzHd6hYmyPQi13nlt5vRc7fABB9Pm2dAl1qRAbDFvsmDx2UxoCh7Dw_wcB
[Pew14]: http://www.pewresearch.org/fact-tank/2014/06/05/generation-x-americas-neglected-middle-child/