---
title: "Engineering Lifecycle"
date: 2018-08-25T21:29:08Z
showDate: true
draft: true
tags: ["blog","opinion"]
---

I suspect that most people involved in engineering will have used, or at least heard of, the [V-diagram](https://en.wikipedia.org/wiki/V-Model), the systems development lifecycle, or something with a similar name. It defines the process of development from requirement through to detailed design, and component test through to acceptance and delivery.

The business I'm in does not involve product design and manufacture, but we still implement a V-shaped engineering lifecycle, and the ideas are similar to those I mentioned above. One problem I experience, however, is that the left-hand side of the diagram is the first to be sacrificed when time pressure is applied. Failure to adequately capture requirements leads to problems later in the lifecycle which can be expensive to put right. Most people I talk to seem to understand the importance of getting requirements right, so why does this stage get discarded so readily?

As with most situations, there are most likely several reasons for this. Perhaps an experienced engineering team is confident that the requirements are well understood even without formally completing the requirements capture phase. Or perhaps, given time pressure, the only chance of completing the task is to get started on the design/implementation as soon as possible. (This also implies some additional assumptions are made: that the design element -- the bottom of the V-diagram -- is the most important, the most time-consuming and the foundation of the entire task; that the requirements are optional and maybe even unnecessary; and that time spent on requirements capture is time stolen from design.)

Recently I've taken an interest in good planning, and therefore requirements capture. In trying to model the advantages of getting the requirements right, and the problems associated with not doing so, I've attempted a different visualisation of the process.

## Why do we use V-diagrams?

The process we follow is essentially linear. We should start at the beginning, eliciting requirements, producing a solution, planning how to implement that solution, doing the work, and then testing, verifying and validating the solution, be it a product or a service. It's true that each stage may loop around with a degree of rework, but in general those loops are constrained within each phase of the process.

The "V" of the lifecycle is intended to enable the result of the work to be somehow measured against what was required. Tests may be verified against a specification, and a product validated against the customer's needs. The "V" becomes useful to illustrate this, showing the appropriate level at which to measure the performance of the product, system, or component.

{{< figure src="https://docs.google.com/drawings/d/e/2PACX-1vSvPYQIV88xrdEVFzIpHqxZOleRNYK7BIsHIRY8d0SQP8GgY3bFg-2zi5dhZcXBTL1xM4NtKeI6tDRw/pub?w=960&amp;h=720" title="V-diagram" >}}

## Tweaking the diagram

I'm quite a visual thinker: diagrams are how I try to explain concepts to people. A lot of diagrams flow from left to right, or top to bottom, and in general, I think diagrams can exhibit a degree of gravity. For example, we talk about conceptual pillars of organisations that support the aims of a company, but those pillars themselves need to be built upon strong foundations.

Taking these concepts a bit further, what could we do with the V-diagram to instil more emphasis on requirements capture? Let's flip the diagram.

{{< figure src="https://docs.google.com/drawings/d/e/2PACX-1vRhJDGku34WKP6-l4rCrZp5vNhjubr4DjyFEFB5cH839Brogenae8vJ3Vg9rQ4A7MXefaY7nMnS55rh/pub?w=960&amp;h=720" title="Inverted V-diagram" >}}

This "lambda diagram" introduces two new concepts:

1. Requirements and validation form the foundation of the activity
2. A task's 'gravity' works against you until you have a good plan, but works with you once you design and test your product

### Requirements are the foundations of your project

If you don't get your requirements right, you will struggle to deliver. On many projects in the past, the left hand side of the V-diagram is not treated with the importance it deserves, and everybody rushes to start work. It's only once the work is complete and it's noticed that it doesn't actually answer the exam question that people realise there was misunderstanding of the actual requirement.

If you take the time to fully understand your customer's requirements, then you have established the basis for validating your product at the end of the project.

### Define your requirements in detail

Your customer wants a widget, right? Wrong. Even if they say that's what is required, it most likely isn't. Your customer might have a need that *results* in a widget, but you should focus on that need first. What problem do they need solving?

Once the customer's requirement is understood, you can proceed to derive a comprehensive set of system-level requirements. Now, in a manufacturing world this is where a requirement can become more tangible. You may be able to define the interaction of a future product with its environment and define requirements based on that.

If you do not produce "things", then what can you do here?

Whatever your customer needs, there will be some scope for that need and a boundary within which the need exists. The key is to define that scope and boundary, to minimise the amount of extraneous work.

Emma wants some advice about the procurement of a new anti-rodent system. She might ask you to tell her which rat trap is the best, but really her problem is about rodent infestation. Knowing that, how can you define the scope of the problem, or the boundary that your solution will sit within?

You discuss the problem with Emma and establish that she requires some form of pest control -- traps might not be the only solution. Further definition of the requirement begins to outline the boundary:

* The problem exists in a large, rural environment
* Regular inspections are not readily feasible
* Abundant wildlife is a concern


