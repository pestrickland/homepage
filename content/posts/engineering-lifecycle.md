---
title: "Engineering Lifecycle"
date: 2018-08-25T21:29:08Z
showDate: true
draft: false
tags: ["blog","opinion"]
---

I suspect that most people involved in engineering will have used, or at least heard of, the [V-diagram](https://en.wikipedia.org/wiki/V-Model), the systems development lifecycle, or something with a similar name. It defines the process of development from requirement through to detailed design, and component test through to acceptance and delivery.

The work I do does not involve product design and manufacture, but we still implement a V-shaped engineering lifecycle, and the ideas are similar to those I mentioned above. One problem I experience, however, is that the left-hand side of the diagram is the first to be sacrificed when time pressure is applied. Failure to adequately capture requirements leads to problems later in the lifecycle which can be expensive to put right. Most people I talk to seem to understand the importance of getting requirements right, so why does this stage get discarded so readily?

As with most situations, there are most likely several reasons for this. Perhaps an experienced engineering team is confident that the requirements are well understood even without formally completing the requirements capture phase. Or perhaps, given time pressure, the only chance of completing the task is to get started on the design/implementation as soon as possible. (This also implies some additional assumptions are made: that the design element -- the bottom of the V-diagram -- is the most important, the most time-consuming and the foundation of the entire task; that the requirements are optional and maybe even unnecessary; and that time spent on requirements capture is time stolen from design.)

Recently I've taken an interest in good planning, and therefore requirements capture. In trying to model the advantages of getting the requirements right, and the problems associated with not doing so, I've attempted a different visualisation of the process.

## Why do we use V-diagrams?

The process we follow is essentially linear. We should start at the beginning, eliciting requirements, producing a solution, planning how to implement that solution, doing the work, and then testing, verifying and validating the solution, be it a product or a service. It's true that each stage may loop around with a degree of rework, but in general those loops are constrained within each phase of the process.

The "V" of the lifecycle is intended to enable the result of the work to be somehow measured against what was required. Tests may be verified against a specification, and a product validated against the customer's needs. The "V" becomes useful to illustrate this, showing the appropriate level at which to measure the performance of the product, system, or component.

{{< figure src="https://docs.google.com/drawings/d/e/2PACX-1vSvPYQIV88xrdEVFzIpHqxZOleRNYK7BIsHIRY8d0SQP8GgY3bFg-2zi5dhZcXBTL1xM4NtKeI6tDRw/pub?w=960&amp;h=720" title="V-diagram" >}}

## Tweaking the diagram

I'm quite a visual thinker: diagrams are how I try to explain concepts to people. A lot of diagrams flow from left to right, or top to bottom, and in general, I think diagrams can exhibit a degree of *gravity*. For example, we talk about conceptual pillars of organisations that support the aims of a company, and that those pillars need to be built upon strong foundations.

Taking these concepts a bit further, what could we do with the V-diagram to instil more emphasis on requirements capture? Let's flip it.

{{< figure src="https://docs.google.com/drawings/d/e/2PACX-1vRhJDGku34WKP6-l4rCrZp5vNhjubr4DjyFEFB5cH839Brogenae8vJ3Vg9rQ4A7MXefaY7nMnS55rh/pub?w=960&amp;h=720" title="Inverted V-diagram" >}}

This "lambda diagram" introduces two new concepts:

1. Requirements and validation form the foundation of the activity
2. A task's 'gravity' works against you until you have a good plan, but works with you once you design and test your product

### Requirements are one side of your project's foundations

If you don't get your requirements right, you will struggle to deliver. On many projects in the past, the left hand side of the V-diagram was not treated with the importance it deserved, and everybody rushed to start work. It was only once the work was complete and it was noticed that it didn't actually answer the exam question that people realised there was misunderstanding of the actual requirement.

If you take the time to fully understand your customer's requirements, then you have established the basis for validating your product at the end of the project.

### Validation holds up the other side of the project

Even if you manage to capture the customer requirements correctly, you still need a plan to check whether the output of your project meets those requirements. A lot can happen between the requirement being defined and the delivery of the finished product. *Scope creep* is one big culprit in the divergence of the project away from its requirements and this can lead to delays and overspends. So whilst the customer agreed to a feasibility study and paid £10k for delivery within a month, delivery of a preliminary design two months late and at double the price clearly is not a valid solution.

Now, it may be that some people in the team believed that the customer was wrong to ask for that study, and that putting in the extra work at this point in a longer programme of work would be beneficial in the long run (based on the team's experience). That still doesn't change the fact that the validation fails. Instead, it shows that the project was built on inadequate foundations. The requirements were captured incompletely, and any validation plans put in place did not consider whether delivery of the customer's request was actually the best thing to be delivering. Had more time been spent at the requirements/validation stage, those people on the team could have discussed their thoughts with the customer, and the requirements could have been revised before the contract was signed, leading to a happy customer who got ultimately found themselves in a better position earlier in the programme than they thought they could be.

## Summary

By considering the V-diagram in an inverted form, we have put the requirements and validation at the foundation of our project. With a solid foundation in place, we should be able to progress to the next step with confidence, and I'll cover that in the next post.

