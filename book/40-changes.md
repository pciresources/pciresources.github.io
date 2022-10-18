---
layout: page
title: Summary of changes in the 4.0 edition of the book

categories: []
tags: []
status: publish
type: page
published: true
meta: {}
toc: false
---

*Back to [books home](/book)*

### Summary of changes in the 4.0 edition of the book

The original 3 volumes were written between fall 2014 and summer 2015 for PCI DSS 3.1; the fourth in 2017 for 3.2. They were only slightly modified based on changes from PCI DSS 3.1 to 3.2 and 3.2.1.

This version includes many more changes including:
* Terminology (see 1.8.7.1) 
* Requirement changes both language and numbering
  * All numbers are from 4.0, but the equivalent 3.2.1 number is present if available, e.g:
    * 12.5.1, v3#2.4
* Images 
  * Mostly updated (design, printing in black and white, etc.)
  * A few removed, some more diagrams added where it helps understanding (and/or will be required for training)

* Section changes (with one goal being reducing page counts from over 450 to ~400)
  * Volume 1
    * Added 1.5.4 - overview of other PCI standards (since removal of PA-DSS)
    * Added 1.6.2 – overview of zero trust (vs castle metaphor of 1.6.1)
    * Changed 1.8.7 to cover changes to PCI DSS 4.0
    * Removed 1.9 (Verizon DBIR and PSR) and 1.10 (Porter 5 forces model) – Look at new 1.9 for logic 
  * Volume 2
    * Added 3 sections (parts of which will be published for free)
      * 2.5.7 PCI Resources Simplified PCI DSS Scoping Model and Approach
      * 2.5.8 Comparison to the PCI SSC Scoping Guidance
      * 2.5.9 Comparison to the OPST
    * Restructured 2.6 (scope reduction) and 2.7 (advanced scoping) for more logical approach and better readability 
      * Added content for eCommerce (a little for SPoC/CPoC) (2.7.1 ++)
      * Modified 2.7.4 Scope of Remote desktop solutions? (was 2.6.5) to clarify scoping impact 
      * Added 2.7.5 Scope of Emails and Instant Messaging Solutions – i.e. Office365/Gmail and similar are not compliant (and you can’t make them), and what would be required for a compliant offering
  * Volume 3
    * Restructured 
      * 3.7.1 and subsections (Req.1) due to removal of need for DMZ, and changes to trusted/untrusted 
      * 3.7.6 and subsections (Req.6) to follow changes in 4.0
      * Added section 3.7.11.5 Changes to payment pages
    * Restructured 3.8 with 6 subsections covering 12.3 (Targeted Risk Assessments) 12.6, 12.8/12.9, 12.10, 12.4 (SP compliance), A1
    * Section 3.9 - updated to newly published prioritized approach 
    * Moved 3.10 to 3.10.1 (Compensating Control) to add a section on the Customized Approach (3.10.2)
    * Removed mappings to ISO 27001/2 and COBIT 5, and my mapping (see 3.12)
  * Volume 4
    * No section changes
  * Appendix A1 – Model – slightly updated
  * Appendix A2 – No major changes
  * Appendix A3 – Added 2 sections (A3.1.1 Encoding is not encryption, A3.5 Evolving Cryptography and its Usage)
  * Appendix A4 – No major changes
  * Appendix A5 – No major changes
