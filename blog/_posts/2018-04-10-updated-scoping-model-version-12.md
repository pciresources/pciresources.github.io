---
layout: post
title: Updated Scoping Model (version 1.2)
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---

I'm happy to announce the release of the update for the 
[PCI Resources Scoping Model and Approach to version 1.2](/pci-dss-scoping-model-and-approach). The model is still available under a creative commons license (CC-BY-SA).

The update is extracted from the most recent version of volume 2 of the book series (paperback called "
[PCI DSS made easy](/book/)", or individual digital volumes) released in December 2017. The major changes were addressing the PCI SSC (PCI council) supplement called "Guidance for PCI DSS Scoping and Network Segmentation".

As I noted in a prior blog post over the other public model (OPST), my major gripe with other explanations was how to deal with segmentation. The same applies with the council’s guidance. I initially included segmentation as part of the CDE, while the PCI SSC document places it within the connected systems. This difference is not that critical for scope, but it can lead to confusion. The PCI DSS standard does state that:

>Without adequate network segmentation (sometimes called a "flat network") the entire network is in scope of the PCI DSS assessment. (PCI DSS 3.2, p.10)


My understanding (and I believe most assessors and experts) is that in the absence of segmentation every system is a CDE system; to state it another way, without segmentation, there can be no connected systems.

To clarify this issue, I've split segmentation systems within their own category. This  does not change in the least my understanding of scope, but I feel it is warranted to, as I already stated, prevent confusion. This is the only major change in the update.

I’ve restructured the model website page to include PDF versions in both US letter and A4 (for my European friends) version of the model, and since translations of the book to my native French and my very fluent Spanish are underway (I will do revisions of the translations to ensure the message is the same in all versions), I will be adding versions of the model in those languages once translations are complete (hopefully by summer 2018).
