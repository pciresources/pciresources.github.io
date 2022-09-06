---
layout: post
title: December 2016 PCI council scoping guidance vs PCI Resources model
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---

The PCI council (PCI SSC) finally released its promised 
[guidance on scoping and network segmentation](https://www.pcisecuritystandards.org/documents/Guidance-PCI-DSS-Scoping-and-Segmentation_v1.pdf) on December 9, 2016 (and I think they did a good job). As with all other information supplements they produce, this guidance is strong recommendation but leaves space for interpretation. Your assessor still (QSA,  ISA, or other such as yours truly) has ultimate say in these matters;  he or she is also receiving more guidance from the PCI council. The PCI Guru has covered this with 
[initial opinions](https://pciguru.wordpress.com/2016/12/10/the-council-releases-draft-scope-and-network-segmentation-information-supplement/) and through answers in a 
[webinar](https://pciguru.wordpress.com/2016/12/15/the-council-speaks-on-a-number-of-topics/) from the council (both posts are recommended reading).

I had started work on another article presenting key differences with PCI zones to network security zones, but as this guidance is relevant, I’ll cover this first and get back to the other article shortly.

This new PCI council guidance aligns well with the 
[PCI Resources scoping model and approach](http://www.pciresources.com/pci-dss-scoping-model-and-approach/) that I first released in summer 2015. This is not surprising as I had shared the model with the council around the time it was released and they had mentioned that they liked my approach. Whether I influenced their thinking or simply aligned with it is beside the point, the important issue is that we are in alignment.

The guidance does add more details than I have in some categories, and has some slight differences that I’ll address here. This new guidance should also be reviewing alongside PCI DSS 3.2 Appendix A3 requirements A3.2 (“Document and validate PCI DSS scope”) that are only currently meant for entities designated by the card brands or their acquirer, but that will likely see inclusion in future versions of the PCI DSS for all entities (merchant, service providers, etc.).

Without further ado, let’s look at the PCI council document.

The introduction and glossary are as one should expect. The only difference is the use of the term “Account data” which is defined as either CHD or SAD, often referred to as PCI data. Although they user “Cardholder Data” in note 7 on the bottom of page 9, which I believe should have used “Account data”.

**Differences with the PCI Resources model**

I still believe that the model I developed works well. If we compare “Figure 1 - PCI DSS Scoping Categories” to my own categories, we find they are similar. The 2 types of CDE systems are exactly what I would call CDE/CHD (called CDE/SPT in earlier versions of my model) and CDE/contaminated.

    
![PCI-Resources-council-scope-vs-model-cde.png](/s/PCI-Resources-council-scope-vs-model-cde.png)


The one main difference seems to be with systems which I call CDE/segmenting, devices that provide (optional) network segmentation. In the PCI SSC guidance, these are considered “Connected-to or Security-impacting Systems” while I consider these to form the edge of the CDE (in my humble opinion, a must since without effective segmentation, there can be no connected systems, only CDE systems). The difference is minimal but at least the guidance makes clear that it is in scope. As I have written in the past, one issue I had with the OPST was the lack of clarity aboutwhether segmentation devices were a type 1 or type 2 system.

    
![PCI-Resources-council-scope-vs-model-connected.png](/s/PCI-Resources-council-scope-vs-model-connected.png)

<!--
![PCI-Resources-council-scope-vs-model-connected.png](https://images.squarespace-cdn.com/content/v1/55934274e4b0d71f69d61a3c/1484582799882-KQGZM4VEJ9D6ZDWN27I4/PCI-Resources-council-scope-vs-model-connected.png)
--> 



The other differences are more stylistic (adding more detail) in what constitutes “connected” systems (called “Connected-to or Security-impacting Systems” in the guidance), specifically those referred to as “connected/security”, and I agree that more detail is better. The other 5 types of “connected systems” (other than segmenting) are:

*System component is on a different network (or subnet or VLAN), but can connect to or access the CDE (e.g., via internal network connectivity) => this is what I call a “connected/communicating” system.


*System component can connect to or access the CDE via another system—for example, via connection to a jump server that provides access to the CDE)  => this is what I call a “connected/indirectly” system.
The other 3 categories they provide are examples of what I call “connected/security” systems:


*System component can impact configuration or security of the CDE, or how CHD/SAD is handled— for example, a web redirection server or name resolution server => this is part of what I call a “connected/security” system.


*System component provides security services to the CDE—for example, network traffic filtering, patch distribution, or authentication management => this is also part of what I call a “connected/security” system.


*System component supports PCI DSS requirements, such as time servers and audit log storage servers => this is also part of what I call a “connected/security” system, but my appreciation of these was more implicit.

Finally, the document provides 4 tests to confirm that a system may be deemed out-of-scope:

*System component does NOT store, process, or transmit CHD/SAD => otherwise it would be a CDE/CHD system.


*System component is NOT on the same network segment or in the same subnet or VLAN as systems that store, process, or transmit CHD => otherwise it would be a CDE/contaminated system.


*System component cannot connect to or access any system in the CDE => otherwise it would be a connected/communicating system (although I still contend that some connections could be considered out-of-scope if one can demonstrate they pose no risk, such as pings...)


*System component cannot gain access to the CDE nor impact a security control for CDE via an in-scope system => otherwise this is a connected/security or connected/indirectly system.

**Network segmentation**

The PCI council guidance did not alter the understanding that was imparted to assessors (I used to be a QSA as well) based on the 
[PCI guru’s comments regarding the webinar he attended](https://pciguru.wordpress.com/2016/12/15/the-council-speaks-on-a-number-of-topics/). The council uses the term “purpose-built controls” to describe the segmentation technology which can include logical or physical controls, or a combination of both, and gives examples of firewalls and routers.

They repeat the relevant portions of the PCI DSS 3.2 standard (p.11) and mention that these technologies are complex and that they must be evaluated. This is exactly the reasoning behind requirement 11.3.4 (footnote: If segmentation is used to isolate the CDE from other networks, perform penetration tests at least annually and after any changes to segmentation controls/methods to verify that the segmentation methods are operational and effective, and isolate all out-of-scope systems from systems in the CDE), 11.3.4.1 which increases testing frequency for service-providers (11.3.4.1 is an almost exact duplicate of A3.2.4)

Ultimately, unless using a straightforward segmentation device such as a physical firewall, entities you should provide an evaluation that covers requirement 11.3.4 demanding network segmentation penetration testing.

**Approach**

On page 9 of the guidance, the PCI council provides the steps of a “typical scoping exercise”. This aligns with the model of my approach to identify scope, but also adds steps to “implement all applicable PCI DSS requirements” and “[m]aintain and monitor” PCI DSS compliance; while I consider these important compliance program steps, my understanding is they fall outside what scoping should include.

**Conclusion**

I found the guidance to be useful, but I still think categorising systems using a model like mine is useful for all but PCI DSS experts, and that it can assist in communication between individuals with different technical levels. The council guidance can serve to confirm whether a system is actually in scope. To me, categorization to adequately documenting scope and performing the required risk assessment of requirement 12.2 (annually and upon significant changes) whose goal is to ensure that risks not covered by PCI DSS (which covers basic information security best-practices and controls) are addressed by the entity (which equates to some form of threat modeling IMHO).

What are your thoughts on the new guidance?
