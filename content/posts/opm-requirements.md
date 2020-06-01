---
title: "Object Process Modelling"
date: 2020-05-25T13:57:32Z
showDate: true
draft: true
tags: ["blog","systems-thinking", "OPM"]
---

## How to handle a customer request

A customer is expected to write a requirement that is sent to us. We would then act on that requirement. Alternatively, the skilled engineer will work with the customer to define the requirement. This approach is preferable and offers the following advantages:

* Saves time -- avoids the back and forth required to iterate and agree the requirement
* Reduces risk -- working with the customer helps to avoid confusion or misunderstanding of ambiguous requirements

Working with the customer isn't without some disadvantages:

* Risks saying yes too quickly
* Risks being too eager to please
* Risks groupthink between the customer and subset of engineering team

The  problem we have is in converting the request from the customer into something that is appropriate for our needs. What we need to do is elicit the requirements in a structured or formal manner. For example what we need to determine is:

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

Our work needs to be traceable. We provide value by being able to trace the history of our advice back across many years.

It makes sense for us to be able to trace the requirements behind our approach. Why did we choose to do something in a particular way?

## Using a model

We use models all the time as part of the design of a system, or to help simulate its performance, or to predict trends. What about with requirements? Not so much.

I'll focus on our unique case later, but generally, most of us will be familiar with a system requirements specification, or similar document at either a lower level of detail or higher level of abstraction. You know the type: a big DOORS export that is essentially a big table of requirements, all written in natural language (English in my experience). Some effort may have been expended in breaking down the requirements in an apparently rigorous way, but often the supporting attributes contain a lot of boiler plate text.

I recently found possibly the clearest description of the benefits of using modelling for requirements on [YouTube](https://youtu.be/zhLi8VgKTe4). You specify the requirements of a house using a set of drawings rather than a language-based specification. Now, it could be argued that the design is actually part of the solution, but I think it really emphasises the point that if you can just find the right approach and language, your job can be a whole lot easier.

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


