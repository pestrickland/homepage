---
title: Requirements Engineering
date:
showDate: true
draft: true
tags: [blog, systems-thinking, requirements]
toc: true
---

"Have we done what the customer wanted?" A valid question, yet one that is often asked too late in the project for any corrections to be feasible. Requirements Management is critical to efficient and successful work, yet is often paid lip service if it is considered at all.

## How to handle a customer request

A customer is expected to write a requirement that is sent to us. We then act on that requirement. Alternatively, the skilled engineer will work with the customer to define the requirement. This approach is preferable and offers the following advantages:

* Saves time -- avoids the back and forth required to iterate and agree the requirement
* Reduces risk -- working with the customer helps to avoid confusion or misunderstanding of ambiguous requirements

Working with the customer isn't without some disadvantages:

* It risks the eager engineer saying yes too quickly
* Being too eager to please (in order to [receive praise]({{<ref "what-drives-us">}})) can taint the "correct" response
* It increases the chance of *groupthink* emerging between the customer and the engineering team

Regardless of the initial approach, the  problem we have is in converting the request from the customer into something that is appropriate for our needs. What we need to do is elicit the requirements in a structured or formal manner. For example, what we need to determine usually includes:

* Assessment boundary
* Scope
* Time constraints
* Priority
* Options
* Regulations
* Standards
* Safety
* Compliance
* Capability

The challenge, then, is to develop a system that rigorously interrogates the requirement and structures or formalises it in a way that is clear and unambiguous, and forms the success criteria against which the solution is measured. Getting the requirements right, in other words, maximises the chance of a successful project delivering quality at an appropriate cost and in good time.

So how do we do this?

### Initial requirements capture

<!-- Not related to the idea of structuring requirements -->
Our work needs to be traceable. We provide value by being able to trace the history of our advice back across many years. With this in mind, it makes sense for us to be able to trace the requirements behind our approach. Why did we choose to do something in a particular way?

#### Using natural language

I'll focus on our unique case later, but generally most of us will be familiar with a system requirements specification, or similar document at either a higher level of detail or higher level of abstraction. You know the type: a big DOORS export[^1] that is essentially a big table of requirements, all written in natural language (English in my experience). Some effort may have been expended in breaking down the requirements in a rigorous way, but often the supporting attributes contain a lot of boiler plate text and duplication, all of which make the document difficult to read.

[^1]: There are two things to note here: firstly, that I am describing requirements that have been *taken out* of a requirements management tool and reproduced on paper; secondly, because of the first point, it's possible that there is much more rich contextual information about the requirements that is lost when a simple table is produced.

Taking our customer requirement, we could document a requirement like this:

1. The solution shall be delivered no later than 31 December 2020
2. The solution shall be reported in accordance with regulation X
3. The supplier shall provide updates at least once per month
4. The solution shall be provided in a PDF format
5. The supplier shall assess risk against the provided criteria
6. and so on...

It's easy to see how a large list of requirements could be produced and keeping them organised can be a problem. More critical is how to ensure that all aspects of the requirement have been captured. Starting from a blank sheet of paper is problematic and can lead to things being missed.

A structured template could help with this. The requirements listed above could be organised into two main categories:

* Delivery requirements
  * Delivery dates, including updates
  * Delivery format
* Definitions
  * Regulations to be used
  * Definitions or assessment criteria

By using a structure like this as a checklist, it is easier to determine whether or not anything has been forgotten. For the more visual thinkers, this can be simply illustrated using a diagram. This takes us into a basic modelling approach.

{{<rawhtml>}}
<style type="text/css">
  #container {
    max-width: 100%;
    height: 480px;
    margin: auto;
  }
</style>
<div id="container"></div>
<script src="/js/vendor/sigma.js-1.2.1/build/sigma.min.js"></script>
<script src="/js/vendor/sigma.js-1.2.1/build/plugins/sigma.parsers.json.min.js"></script>
<script>
  sigma.parsers.json('/data/data.json', {
    container: 'container',
    settings: {
      defaultNodeColor: '#fa8334'
    }
  });
</script>
{{</rawhtml>}}

#### Using a model

Models are frequently used as part of the design of a system, or to help simulate its performance, or to predict trends. What about with requirements? It's not so clear.

Looking at the example above, the structure of the requirement categories is the beginning of a model. With additional context and attributes added to each item, it would be possible to produce a requirements model that develops the initial customer requirement to cover all the aspects in the graph. It doesn't have to be graphical of course; the same result could be achieved in a table, with one requirement per row and numerous attributes to further define the requirement. In *Requirements Engineering*[^2] a large list of attributes is presented, including:

[^2]: Hull, E.C, Jackson, K. and Dick, J.J, *Requirements Engineering*, Springer, 2002.

* Unique identifier
* Basic type
* Lifecycle phase
* Priority
* Importance
* Derivation type
* Source
* Owner
* Approval authority
* V&V method
* Status
* Rationale
* Maturity
* Risk level

The large size of this list is daunting, yet it is easy to see how such detail can be useful to fully define a set of requirements. But before I embarked on trying to develop a system to more rigorously apply a comprehensive system of requirements engineering to my work, I was interested to see what other types of model, if any, might exist.

I recently found what I think is the clearest explanation of the benefits of modelling requirements by Contrux Software's [Brain Bytes.](https://youtu.be/zhLi8VgKTe4) You specify the requirements of a house using a set of drawings rather than a language-based specification. Now, it could be argued that the design is actually part of the solution, but I think it really emphasises the point that if you can just find the right approach and language, your job can be a whole lot easier.
