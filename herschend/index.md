<!-- markdownlint-disable first-line-h1  -->
<!--
 cSpell:ignore herschend herschend's xers snapchat pokéman united's
 cSpell:ignore tibco corba dcom msmq brokerless amqp mqtt rtos devops
 cSpell:ignore pdlc antifragile
-->

# Herschend Director of Enterprise Web Architecture Position Analysis

**Kenneth Brubaker<br>
2017-02-19**

<p align="right">
<i>— <a href="https://github.com/clavecoder/clavecoder.github.io/commits/master/herschend/index.md"
        target="_blank">document history</a></i>
</p>

![document status](https://img.shields.io/badge/document_status-DRAFT-0101aa.svg)

<!-- markdownlint-disable ul-style -->

> ## Table Of Contents
> - [Executive Summary](#executive-summary)
> - [Caveat](#caveat)
> - [Introduction](#introduction)
> - [Distributed Systems](#distributed-systems)
> - [DevOps](#devops)

<!-- markdownlint-enable ul-style -->

## Executive Summary

- Introduction
  - Author shares misgivings about preparing an analysis with so little
    information
  - A new software architecture is needed to capture the opportunities
    provided and challenges posed by the next decade
  - A Director of Enterprise Web Applications provides a hub around
    which to develop and deliver that architecture
- Distributed systems
  - A history of distributed systems is discussed
  - Current distributed systems technologies are discussed
  - A formal product review process is essential to determine the
    appropriate technology for Herschend. The approach is discussed
    elsewhere in the document

## Caveat

![section status](https://img.shields.io/badge/section_status-Review-ADAD01.svg)

I've been asked by Jon Dilly at **iStaff** to provide an analysis of the
Director of Enterprise Web Architecture position at Herschend. I don't
feel very comfortable providing an analysis with only a few hours of
conversation but with the caveat that my assessments may change as I
learn more about Herschend and it's business, I will proceed with what I
feel may be a reasonable approach to the position.

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
Wi-Fi modules to be had for as little as $1 [\[GBMod\]][GBMod], no
longer should we consider machinery as merely mechanical or electrical
systems. Moreover, the prospect of connected devices provides
unprecedented opportunity for preventing and mitigating downtime of
entertainment and amusement center rides and for providing more
opportunities to delight guests.

### A new connected architecture

To meet the opportunities and challenges that Herschend faces in the
coming decade, a new distributed and connected architecture must be
envisioned and enacted using technologies and practices to which Herschend
has not been used in the past. A qualified Director of Enterprise Web
Architecture provides a nexus around which to plan, construct, and
deliver distributed and connected software systems to meet the needs of
the 2020's

## Distributed Systems

![section status](https://img.shields.io/badge/section_status-Review-ADAD01.svg)

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

While in the past debates have raged and large sums of money have been
consumed over the issue of how to best connect distributed systems, much
of the industry has settled down to using REST for customer facing
systems and combination of more specialized messaging systems
internally. These include lightweight brokerless technologies such as
ZeroMQ, and brokered messaging protocols. Major players include Kafka,
RabbitMQ, and the Advanced Message Queuing Protocol (AMQP) compliant
ActiveMQ. For device networks, i.e., Internet of Things (IoT), MQTT
is often used unless a real-time operating system (RTOS) is required. For
logging and monitoring communication, Kafka and StatsD are frequently
used along with a plethora of proprietary monitoring protocols and
services.

As cloud based providers have exploded in size and number, the balance
of power has shifted away from the gridiron software vendors to cloud
software providers creating and sharing their own protocols and
implementation. Most of the technologies just mentioned fall into this
category. Since software development at scale has been democratized with
the advent of cloud hosting, software providers have looked for ways to
increase software delivery velocity.

To facilitate independent deployment of system capabilities,
enterprises have increasingly have turned away from the *smart pipes*
approach which enforces a high degree of coupling between components
and the central system. Instead, they have turned to a *smart endpoints*
approach employing teams of developers delivering independent systems
within the organization that interact over standard protocols, most
especially REST, which can be considered the universal protocol.

### Distributed systems choices

That Herschend sees the need to adopt distributed computing principals
has already been expressed by several staff members. While, perhaps not
the most critical technology choice to be made for short term success,
it is nonetheless vital to the long term competitive advantage for
Herschend with respect to their systems integration capability in an
increasingly connected world. Equally important a misstep in choice of
technology or execution could be very costly. It is, therefore, very
important that a detailed investigation and formal product review be
executed early in the planning stage of the initial project. The method
of the formal product review is discussed elsewhere in this document.

## DevOps

![section status](https://img.shields.io/badge/section_status-DRAFT-0101aa.svg)

### Product lifecycle

It is a truism that all applications and software technologies undergo a
product lifecycle: they are introduced, enhanced, maintained, contained,
and retired. As with any other depreciating asset, it is incumbent on
the organization to manage the lifecycle of of these applications and
technologies to the best possible advantage of the business. It falls to
the Management of Information Systems (MIS) department to perform this
function. This process is what is called Product Portfolio Management
(PPM). The author has seen many enterprises, who so often are careful of
other forms of asset responsibility, not know the need or how to acquire
the skills to perform this needed function.

All enterprises have a portfolio of Commercial off the shelf (COTS)
applications and custom developed applications. Some are internal
corporate housekeeping applications and other are client facing
applications that are strategic for their business operation and
advantage. Besides human capital and sometimes real estate, applications
and the infrastructure to host them can be among the most costly
expenses an enterprise has. Moreover, this software is frequently
essential for corporate success. Application breakage, data center
outages, and enterprise data loss in some systems can cause
catastrophic failure of an organization.

In addition, the ever increasing pace of change in technology and the
incessant push to increase productivity through systems integration
and real-time access, place increasing strains on information systems
department to deliver software capabilities that at the pace and
availability that the business need require.

An important component of PPM is the planing and execution of product
change known as the Product Development Lifecycle (PDLC). Many
organizations, as they grow, tackle software product issues as they
develop or become aware of them. As they grow, they begin to find that
the ad-hoc process fails them as many critical needs to revamp obsolete
software or provide strategic enhancements out strips their immediate
resources. In short, non-technology companies they find it difficult to
acquire this important capability and proficiency to plan and execute
software product change.

It is in these areas of PPM and PDLC that Herschend sees
challenges and opportunities as it ponders how it will approach the
coming decade. If it can organize itself to approach PPM and PDLC to
capitalize on the change required to support future distributed systems,
Herschend can transform the risk involved to significant advantage.

### From Application lifecycle to DevOps

Traditional approaches to application change involve yearly planning
meetings and PDLC execution cycles of one or more years. For custom
developed applications there is an associated software change capability
known as the Software Development Lifecycle (SDLC) and associated
software feature management proficiency known as Application Lifecycle
Management (ALM). It is this areas of SDLC and ALM that the author has
many years of experience operating within the context of the larger
PPM governance and PDLC process in entities of all sizes over the span
of 26 years.

Certainly, many changes have occurred within the industry over the
years, however it the adoption of Agile development practices that has
truly transformed the way software products are managed.

The driver of this adoption curve are the huge cloud-native software
providers, as discussed briefly in the previous section on distributed
systems. These large software providers have released the tools they use
to enable this continuous, global-scale deployments free of charge to
the community. Since even the smallest company can now be a global,
high-availability entity that can roll out change almost instantly, the
competitive advantage of larger entities that can stand up large data
centers and afford expensive vendor development and deployment tools is
now lost. Even the largest organizations now need to acquiesce to this
new reality.

The name of this new reality, in a word, is DevOps; that is, the marriage
of Development and Operations into a single continuum. Using open tools
provided to the community by and maintained with the support of larger
organizations, any size company can reap the benefits of DevOps — if
they are able to make the organizational changes necessary.

Having the tools for DevOps provide little benefit if the processes to
support it are not also present. These new processes include Agile
development methodologies such as Scrum and Lean, Test Driven
Development (TDD), Continuous Integration (CI), Continuous Delivery
(CD), Antifragile software design, A/B testing, and many more. But it is
Agile Development that is most transformative as it underpins and
enables the other processes. When taken as a whole, DevOps enables the
unresponsive traditional PDLC process into a very responsive software
factory enabled through DevOps.

### Agile product delivery

The business needs of the next decade cannot be met using traditional
product and software development practices. Agile development practices
bring the PDLC and SDLC processes together through the use of the
Product Backlog and inclusion of a Product Owner as a member of an Agile
Team who works with product managers and empowered to make detailed
business decisions as part of the team.

Once product management is drawn within the software development process
and DevOps pulls product delivery within the software development
process, the enterprise now has the means to deploy business features
as swiftly as possible, enabling even the testing of business questions
and theories without overbearing development time and costs.

All of this is possible only if the organization is changed into a
cross-functional process where product management and software delivery
becomes a continuous process.

### The importance of automation



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