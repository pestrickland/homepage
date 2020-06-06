---
title: "Object Process Modelling"
date: 2020-05-25T13:57:32Z
showDate: true
draft: true
tags: ["blog","systems-thinking", "OPM"]
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

Our work needs to be traceable. We provide value by being able to trace the history of our advice back across many years. With this in mind, it makes sense for us to be able to trace the requirements behind our approach. Why did we choose to do something in a particular way?

#### Using natural language

I'll focus on our unique case later, but generally most of us will be familiar with a system requirements specification, or similar document at either a lower level of detail or higher level of abstraction. You know the type: a big DOORS export[^1] that is essentially a big table of requirements, all written in natural language (English in my experience). Some effort may have been expended in breaking down the requirements in an apparently rigorous way, but often the supporting attributes contain a lot of boiler plate text.

[^1]: There are two things to note here: firstly, that I am describing requirements that have been *taken out* of a requirements management tool and reproduced on paper; secondly, because of the first point, it's possible that there is much more rich contextual information about the requirements that is lost when a simple table is produced.

Taking our customer requirement, we could document a requirement like this:

1. The solution shall be delivered no later than 31 December 2020
2. The solution shall be reported in accordance with regulation X
3. The supplier shall provide updates at least once per month
4. The solution shall be provided in a PDF format
5. The supplier shall assess risk against the provided criteria
6. and so on...

It's easy to see how a large list of requirements could be produced and keeping them organised can be a problem. More critical is how to ensure that all aspects of the requirement have been captured. Starting from a blank sheet of paper is problematic and can lead to things being missed.

A structured template could help with this. The requirements listed above could be organised into two categories:

* Delivery requirements
  * Delivery dates, including updates
  * Delivery format
* Definitions
  * Regulations to be used
  * Definitions or assessment criteria

By using structure like this, it is easier to determine whether or not anything has been forgotten. For the more visual thinkers, this can be simply illustrated using a diagram.

{{<rawhtml>}}
<style type="text/css">
  #container {
    max-width: 400px;
    height: 400px;
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
      defaultNodeColor: '#ec5148'
    }
  });
</script>
{{</rawhtml>}}

#### Using a model

Models are frequently used as part of the design of a system, or to help simulate its performance, or to predict trends. What about with requirements? It's not so clear.

I recently found what I think is the clearest explanation of the benefits of modelling requirements on [YouTube](https://youtu.be/zhLi8VgKTe4). You specify the requirements of a house using a set of drawings rather than a language-based specification. Now, it could be argued that the design is actually part of the solution, but I think it really emphasises the point that if you can just find the right approach and language, your job can be a whole lot easier.




## OPM learning

### Objects

Objects are things that can be either physical, tangible things, or things that convey information. They could also be thought of as *nouns*. Object examples include "report" and "temperature".

An object can be connected to a process or to another object.

An object can have a variety of different states. A simple example is "hot or cold", but the states don't have to be directly related. For example a passenger flying could have a number of states affected by different processes, such as "checked in", "boarded", "airborne" and "landed".

#### Specification

* An object is depicted by a rectangle
* An object has a title
* An object can be physical or non-physical
  * Physical objects are depicted with a drop shadow
* An object can optionally have a state

### Processes

Processes are things that happen. Specifically, they do things to objects. They are intangible and could be thought of as *verbs*. Processes can be physical, such as "coffee making", but also "battery charging"

Processes are written along the lines of "coffee making".

A process can be connected to an object or to another process.

#### Specification

* A process is depicted by an ellipse
* A process has a title
* A process can be physical or non-physical
  * Physical processes are distinguished from non-physical processes by having a drop shadow

### Transformation

Transformation is what a process does to an object. This can be one of three things:

* Creating a new object
* Consuming an existing object
* Changing the *state* of an existing object

### Consumption and creation

Consumption is depicted by an arrow that points in the direction of the consumer, so the object of water points towards the process that consumes it.

A newly created object is pointed to by the process that creates it. In other words, things are connected by arrows that depict the direction of the supply, consumption and production of the useful things produced by a process.

## Application to our work

### Objects



### Processes

## What is it that we actually do?

* We don't produce things
* We don't build things
* We don't design things
* We don't assemble things

The examples above are common examples used in systems engineering, as so much of the theory seems to be based in the design and manufacture space. But we don't do that. I think before we go any further we need to establish clearly what it is we *do*.


