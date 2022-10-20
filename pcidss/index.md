---
layout: page
title: PCI DSS Overview
categories: []
tags: []
status: publish
type: page
published: true
meta: {}
---


* This section is adapted from the [books](/book)*

The goal of information security should never be to block anything outright, but only to enable users to perform their legitimate business tasks in a secure fashion.

The goal of PCI DSS is to protect cardholder data from theft or unauthorized disclosure. This is our gold standard, the lens through which we will look at the PCI DSS requirements. And while the goal is to protect data, it is accomplished through measures on people, processes and technologies.

All requirements in PCI DSS are mandatory, unless we can be prove (and adequately document) that they are not applicable to our situation (FAQ 1252). For example, requirement 3.5.1 (v3#3.4) to render "PAN unreadable" (PAN, Primary Account Number, is the payment card number) can only be applicable if a PAN is present.

PCI DSS is not about compliance, it is about security. The problem is that it remains virtually impossible to prove anyone is secure (one can only prove lack of security). So the next best thing is to do an assessment (which is a point-in-time review, not an audit) to ensure that you have basic controls in place.

Indeed, the PCI DSS standard states it that it "comprises a minimum set of requirements for protecting account data" and implies that it may not be sufficient to ensure security. But if you are not compliant, you are likely not secure.

The first step in protecting Cardholder Data (aka Payment Card Information) is to adequately define scope. If you have not review the scoping model and approach, I recommend you review it first as it covers my approach to this.

Any Program Structure, including for PCI DSS and Information Security, is generally divided between a governance head (including policies) and the procedural/technical body, which are further describe in subsequent pages.
