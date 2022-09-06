---
layout: post
title: A better PCI DSS scoping model? Or the problems with the OPST.
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---

I have seen and heard about many ways of classifying systems for PCI DSS or expressing how to go about scoping. The most formal method I have found described out there is in the Open PCI Scoping Toolkit (OPST, http://itrevolution.com/pci-scoping-toolkit/) (which is not endorsed or approved by the PCI SSC). It was released in 2012, though I only learned of it in 2014. While I agree with the general approach to classifying systems, I have disagreements on the categories defined in the OPST. The lack of a model that I felt addressed PCI DSS appropriately is one of the reasons I dedicated a complete 
[volume](/volume-2-toc) to scoping. I’ve decided to open the model under a Creative Commons licence (
[CC BY-SA](https://creativecommons.org/licenses/by-sa/3.0/)) for free to everyone in the hopes that we can all improve scoping and thus better manage our risks. The model is not endorsed or approved by the PCI SSC, though they are aware of it (and the PCI SSC, or PCI Council, has promised scoping guidance for 2016). The model can be found here: http://www.pciresources.com/pci-dss-scoping-model-and-approach/ (a PDF version is also available).


I first want to commend the group who produced the OPST on the work done; it is the most comprehensive one I’ve seen to date. I do however have significant disagreements with some of their interpretation.


In volume 2 of my series on PCI DSS compliance, I address scoping. I present my own methodology derived from the language of the standard (pages 10 and 11). Thus, I prefer the term CDE to category 1, and connected to category 2 (although "category" and "types" have been in PCI Community Meetings in the past).


My two major differences with the OPST are regarding segmentation and the risk posed by different connecting systems, with the main one being with devices that provide segmentation (which I call CDE/segmenting) and which the OPST does not address directly.


In the OPST, a segmenting device (say, a firewall) is either type 1a (CDE/SPT in my model) if it is traversed by a PCI data flow (containing CHD and/or SAD), or type '2a' if it provides security services (connected/security in my model). To me, such a device will always be a part (the edge) of the CDE whether or not it is traversed by a PCI data flow, and subject to the same requirements which apply to all CDE systems. Indeed, you cannot have a connected system (a type 2 in the OPST) unless you have a device that provides segmentation.


There is an instruction to that effect on page 11 (also present since PCI DSS version 1.2 in 2009): "If network segmentation is in place and being used to reduce the scope of the PCI DSS assessment, the assessor must verify that the segmentation is adequate to reduce the scope of the assessment."


The CDE/segmenting sub-category is furthermore warranted by the inclusion of new rules in PCI DSS 3.0 regarding the testing of segmentation during the required annual internal penetration tests (#11.3.4). Section 3.3 (Network Segmentation) of the PCI DSS 3.0 Report on Compliance (RoC) template (version 1.1) also requires this validation of adequate segmentation. Note that the firewall rules that are unrelated to the CDE environment would be out-of-scope.  This could happen if the firewall manages the connection point between the CDE and various other network segments. In that case, only the rules that pertain to access to the CDE are in-scope (for review)


The other difference that I have with the OPST (other than the segmenting devices) is about how each of us define many categories of connected systems based on function and on who can initiate connections, although this difference is less critical than the first. The OPST defines as '2a' those systems that I include as connected/security systems. The OPST also defines systems that can initiate a connection to a CDE system as '2b', and those that can only receive a connection as '2c'.


There is an implication in the OPST that systems that can initiate a connection to a CDE system ('2b') are inherently more risky than systems that can only receive (and not initiate) a connection from a CDE system ('2c'). This is not always the case.


A simple example can explain why I rather not split these up. Let's take two connected systems. The first one has access to ping into the CDE for diagnostic perspectives (a '2b'). This constitutes its only access. The second system is a web application (for example an HR application or an intranet) that can be accessed from a CDE system (a '2c').


Now, most practitioners would agree that both connected systems are in-scope and are subject to all PCI DSS requirements. Other than the famous Windows 95 "ping of death" which is no longer an issue, ICMP packets used by the ping application are fairly safe. And, as a colleague rightly commented in a discussion on this topic, Denial of Service vulnerabilities (such as the “ping of death”) are not even to be reported by an ASV.


On the other hand, the web application, when contacted by a CDE system, will actually return information (text, binary, application, etc.) which could be nefarious in nature (many attacks nowadays use web browsers to infect a target). Obviously, the '2c' system is more risky than the '2b' in this case. For this reason alone, I would rather not split systems that have a connection to the CDE into subcategories ('2b', '2c') and just deal with them as one category called 'connected' (meaning those connected that do not provide security services) and allow users to document how some of these may be out-of-scope.


There is another clarification that I wish to make and that is not just with the OPST, but with other documents as well. In graphical representations such as the diagram on p.15 of the OPST, it can appear that Category 2 (connected) systems need be separate from category 3 systems (out-of-scope). While more segmentation by security levels is a good security best practice, only CDE (category 1) systems need be segmented from other systems.


What do you think? How else should scoping be addressed?
