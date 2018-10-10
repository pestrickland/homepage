---
title: "Engineering Lifecycle"
date: 2018-08-25T21:29:08Z
showDate: true
draft: true
tags: ["blog","opinion"]
---

Most people involved in engineering will have used, or at least heard of, the V-diagram, the systems development lifecycle, or something with a similar name. It defines the process of development from requirement through to detailed design, and component test through to acceptance and delivery.

The business I'm involved with does not involve product design and manufacture, but we still implement our own engineering lifecycle, and the ideas are still sound. The problem, however, is that the left-hand side of the diagram are the first to be sacrificed when time pressure is applied. Failure to capture requirements leads to problems later in the lifecycle which can be expensive to put right. Most people I talk to seem to understand the importance of getting requirements right, so why do this stage get discarded so readily?

As with most situations, there are most likely several reasons for this. Perhaps an experienced engineering team is confident that the requirements are well understood even without formally completing the requirements process. Perhaps, given time pressure, the only chance of completing the task is to get started on the design/implementation as soon as possible. (This also implies some additional assumptions are made: that the design element -- the bottom of the V-diagram -- is the most important, the most time-consuming and the foundation of the entire task; that the requirements are optional and maybe even unnecessary; and that time spent on requirements capture is time wasted on design.)

Recently I've taken an interest in good planning, and therefore requirements capture. In trying to model the advantages of getting the requirements right, and the problems associated with not doing so, I've attempted a different visualisation of the process.

## Why do we use V-diagrams?

The process we follow is essentially linear. We should start at the beginning, eliciting requirements, producing a solution, planning how to implement that solution, doing the work, and then testing, verifying and validating the solution, be it a product or a service. It's true that each stage may loop around with a degree of rework, but in general those loops are constrained within each phase of the process.

The "V" of the lifecycle is intended to enable the result of the work to be somehow measured against what was required. Tests may be verified against a specification, and a product validated against the customer's needs. The "V" becomes useful to illustrate this, showing the appropriate level at which to measure the performance of the product, system, or component.

{{< figure src="https://docs.google.com/drawings/d/e/2PACX-1vSvPYQIV88xrdEVFzIpHqxZOleRNYK7BIsHIRY8d0SQP8GgY3bFg-2zi5dhZcXBTL1xM4NtKeI6tDRw/pub?w=960&amp;h=720" title="V-diagram" >}}

## Tweaking the diagram

I'm quite a visual thinker: diagrams are how I try to explain concepts to people. A lot of diagrams flow from left to right, or top to bottom, and in general, I think diagrams exhibit a degree of gravity. We talk about conceptual pillars of organisations that support the aims of a company, but those pillars themselves need to be built upon strong foundations.

Taking these concepts a bit further, what could we do with the V-diagram to instil more emphasis on requirements capture? Let's flip the diagram.

{{< figure src="" title="Inverted V-diagram" >}}

This "lambda diagram" introduces two new concepts:

1. Requirements and validation form the foundation of the activity
2. Gravity works against you until you have a good plan, but aids delivery of the finished product

### Requirements are the foundation

If you don't get your requirements right, you will struggle to deliver.
