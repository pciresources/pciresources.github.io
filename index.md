---
layout: page
title: A structured approach to the PCI standards
categories: []
tags: []
status: publish
type: page
published: true
meta: {}
toc: false
---

 
## Information on Payment Card Industry (PCI) standards including PCI DSS since 2015

The Payment Card Industry (PCI) standards maintained by the PCI SSC have the stated goal to protect card information. 
My experience that most users can interpret most individual requirements, but lack the overall structured approach (the big picture) to meeting the standards intent. 
The recent update to PCI DSS 4.0 include major rewriting of individual requirements which should help this somewhat.
Still as it is a complex standard, additional guidance can help.

What started as an idea in 2014 to provide what was sorely missing guidance on PCI DSS through books has grown, and should continue to grow, to provide more information and tools based on my experience servicing a variety of clients.

### Books

This site will provide PCI resources to the community, starting with a series of volumes in paper and digital formats ([books](/book)) 
explaining the various facets of the PCI DSS, the main standard maintained by the 
[PCI SSC.](https://www.pcisecuritystandards.org/). 
Links to other valuable resources will also be provided within each page.

The books can be purchased on the 
[Amazon](https://www.amazon.com/Yves-B.-Desharnais/e/B012KZCNTI) kindle store* or the 
[Apple iBooks](https://itunes.apple.com/us/author/yves-b.-desharnais/id1089327373?mt=11) store (for iPad, iPhone and Mac computers).
The 4.0 versions for iBooks will be published late October or early November 2022.

A subscription version application which will provide and link not only my writings, but also various documents from the PCI SSC and others is also in advanced development. 

The [scoping model and approach](/pci-dss-scoping-model-and-approach) I use is available here (for free under a creative commons license) and further described and detailed in 
[volume 2](/book/volume-2-toc).

*Note: Amazon Kindle is a platform and not just a physical reader device. Kindle reader applications exist for iPhone/iPad, Android, PC, Mac, and even on the web.

<!--
### PCI DSS

For more on the PCI DSS, please start with the
[overview](/pci-dss-overview), which links to description of the intent (the objective) of the PCI DSS high-level requirements.

-->

### Tools

A large part of my background, on top of information security, is software engineering and application development. 
This means that when I cannot find a tool (commercial or open source), I can roll my own.
This provides for tools that are optimized to the task at hand. Often very optimized.

Scoping being the main driver behind my work let to the development of [NetBehave](netbehave.org) as a tool to perform data flow analysis (initially using NetFlow/IPFix) for scope identification, validation, and monitoring. More details about the technical aspects on that website. At home, I ran the full tool on a Raspberry Pi 2 using about 500Mb of RAM, that's what I mean by optimized. I am available for paid support of that open source tool.

I also have developped a command-line DLP agent which runs on Windows, MacOS and Linux, whose focus is on reducing false-positives. Feel free to contact me regarding such a tool.

More tools are in development and scheduled for release in the next few months.

#### *Note: A migration and redesign of this website is underway and expected to be completed in September 2022. Expect style changes and much more information shortly. Stay tuned.*

*Dans un avenir rapproché, j'espère fournir une version française du contenu de ce site.*

*En un futuro cercano espero proveer este mismo contenido en español.*
