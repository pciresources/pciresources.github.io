---
layout: post
title: Changes between PCI DSS 3.1 and 3.2
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---

This post was initially published on LinkedIn on October 13, 2016 at 
[https://www.linkedin.com/pulse/changes-between-pci-dss-31-32-yves-desharnais-mba-cissp-pcip?trk=prof-post](https://www.linkedin.com/pulse/changes-between-pci-dss-31-32-yves-desharnais-mba-cissp-pcip?trk=prof-post).

This text is adapted from section 1.8.5 of my book series on PCI DSS. (
[http://www.pciresources.com/pci-dss-book/](http://www.pciresources.com/pci-dss-book/)) and supplemented with information from the 2016 North American PCI Community meetings (PCICM) which I just attended a couple of weeks ago.
As a reminder PCI DSS 3.2 will become the active standard as of November 1, 2016, although new requirements will only become mandatory on February 1, 2018. PCI DSS 3.1 can only be used for assessments ending by October 31, 2016.

As a point release, this version did not change the DSS dramatically. The SSL/TLS changes of PCI DSS 3.1 and a subsequent revision published on December 18, 2015, were integrated in appendix A2 (and requirements using SSL/TLS now point to this appendix). Appendix A3 was added by integrating the DESV (Designated Entities Special Validation) requirements (applicable for designated entities only).

In order to see what has changed in the standard, I created a comparison document in Microsoft Word which I've annotated and am making available as PDF on my website here (no registration required): 
[http://www.pciresources.com/s/PCI-Resources-Changes-to-PCI-DSS-Requirements-31-to-32.pdf](http://www.pciresources.com/s/PCI-Resources-Changes-to-PCI-DSS-Requirements-31-to-32.pdf)

##New requirements for all entities (mandatory by February 2018)


In terms of requirements, PCI DSS 3.2 introduced only two new requirements for all entities (merchants and service providers):

*A new requirement (6.4.6) was added within the change control section (6.4.*) aiming to ensure that the entity maintain compliance with PCI DSS. Any changes that touches on any in-scope “system components” (that list must be maintained per requirement 2.4 and in the scope documentation that should be maintained) must be reviewed before change is approved. A change that may affect the scope or the security of the CDE needs to be evaluated before the change takes place to ensure no lapse in compliance.


*Two-factor authentication was renamed to multi-factor authentication (only the name changed) and expanded (8.3 is now 8.3.2) and a new sub-requirement 8.3.1, was introduced to address the risk of phishing on IT administrators by requiring multi-factor authentication for administrative access to CDE systems.

##New requirements applicable only to Service Providers (mandatory by February 2018)


There were also a few new requirements applicable to service providers only (the PCICM mentioned they were adapted from the DESV in Appendix A3):

*A new documentation requirement (3.5.1) mandating the documentation of the cryptographic architectures.


*A new set of requirements to monitor for failures of critical security controls (10.8) and treat failures as incidents (10.8.1); this ties back to requirement A3.3.1 in Appendix A3.


*A new requirement (11.3.4.1) for testing network segmentation every six months (instead of every year); this ties back to requirement A3.2.4 in Appendix A3.


*A new requirement (12.4.1) mandating the assignment of responsibility for the protection of cardholder data and a PCI DSS compliance program; this ties back to requirement A3.1.1 in Appendix A3.


*A new set of requirements to perform quarterly reviews to confirm personnel are following security policies and operational procedures (12.11) and treat failures as incidents (12.11.1); this ties back to requirement A3.3.3 in Appendix A3.

##Clarifications to individual requirements (applicable by November 2016)


While most other changes were clarifications to the requirements that do not affect their intent as understood by most assessors, there were a few substantive changes that will be applicable this November:

*Requirement 1.3.5 (moved from 1.3.6 as 1.3.3 was removed) removed “stateful inspection” and replaced it with “permit only “established” connections into the network.” as there are stronger options available (evaluation left to the assessor); this should not change most assessors' understanding of the requirement.


*Requirement 1.4 for a “personal firewall” for devices changed from “mobile” to “portable” since devices that connect remotely (and/or wirelessly) no longer include only laptops but smartphones and tablets (and potentially more devices). Personal firewalls in laptops, Mobile Device Management (MDM) generally provide this functionality.


*Requirement 11.5 (change detection management) had a change in its test procedures which used to imply that this requirement only applied to CDE systems and not connected ones (see this model for details: 
[http://www.pciresources.com/pci-dss-scoping-model-and-approach/](http://www.pciresources.com/pci-dss-scoping-model-and-approach/) ). It is now clear that all in-scope systems should now be covered by this requirement.

These should be simple changes for merchants, while service providers have a bit more work on their hands.

What changes do you see presenting more of a challenge?
