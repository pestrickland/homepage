---
title: "Project Desk Defender"
description: "I briefly describe an idea to design and build an automatic tracking Nerf gun -- for educational purposes"
tags: ["Desk Defender","STEM"]
date: 2016-05-15
showDate: true
draft: true
---

## Introduction

The beginning of 2016 saw me taking an interest in promoting STEM (science, technology, engineering and mathematics) to young students. This interest emerged after spending several days reviewing CVs and interviewing university students for graduate and industrial placement positions. I was impressed by the academic standard of those people applying, but surprised that applying that knowledge outside of what they'd learnt was something they struggled with.

Based on the experience of this year's applicants, I thought it would be useful to have some sort of involvement with people before they applied, if only to tell them what not to put in their CVs.

Since then, I've joined [STEM Learning](https://www.stem.org.uk/stem-ambassadors/) as an ambassador and have an Arkwright Scholar to mentor. During that time, I've also been brainstorming projects that I could design and manufacture for demonstration of engineering concepts at school. This led to the *Desk Defender* (a working title), and I will document my progress here.

The Desk Defender is a project to essentially combine the technology of a close-in weapon system -- such as Phalanx or Goalkeeper, the latter described on [Wikipedia](https://en.wikipedia.org/wiki/Goalkeeper_CIWS) and shown below (or [here](https://youtu.be/6CHDjOCyixU) on YouTube) -- with the lower destructive capacity of a Nerf-style gun.

{{< youtube 6CHDjOCyixU >}}

## Requirements capture

I wanted to approach this project using good engineering practice as much as possible. So although there was a bit of reverse engineering required, I started with the requirements.

Since there is an educational aspect to this project as well as a personal interest, I included requirements for educational demonstration as well as system requirements. Some of those cross over quite nicely. My requirements were created in [ReqView](https://www.reqview.com/index.html) using the free licence. The main requirements are for a system that:

* Can detect, track and shoot down a paper aeroplane
* Can fire single shots, bursts or fully automatically
* Can be operated manually and automatically
* Has demonstrable safety features
* Is very visual, and well suited to explaining key concepts to people new to engineering

## Design concept

So far, design is in its conceptual stages. Below are my current thoughts about the major systems involved, plus a note about manufacturing considerations.

### Gun system

Part of my early research was into the gun system. Initially I thought of a multi-barrelled, gatling-type machine. However, this might be unnecessarily complicated. Depending on the operating mechanism required for the Nerf-style darts, I thought that a revolver cannon (such as the [Mauser BK-27](https://en.wikipedia.org/wiki/Mauser_BK-27)), or a simple linear bolt action mechanism might suffice.

Looking at Nerf guns themselves, the majority function using a piston to fire the darts using compressed air. However, there is also a flywheel mechanism in use, such as with the [Nerf Stryfe](http://nerf.wikia.com/wiki/Stryfe), where darts are accelerated between two rotating flywheels and into the barrel.

My initial thought was to use the flywheel concept, and to focus my design on the feed mechanism.

### Target detection and tracking

Part of the requirement is to shoot down a paper aeroplane. One option for doing this is to manually control the gun. This is something I'll probably include, perhaps with a radio control system.

What I ultimately want, however, is an automatic detection and tracking system. In real world applications, this is accomplished with radar, which provided range and position information. Goalkeeper, for example, uses one radar to scan the sky for new targets, and another radar to track a prioritised target.

I considered the use of an ultrasonic transducer to imitate a radar system, but the limited range of a few metres led me to discount it. Similarly, a laser rangefinder could be used to scan the scene. Such systems require precise timing due to the speed of light, and have a fairly high cost associated with them.

My eventual plan was to look at image processing and motion detection. Using a USB video camera, I would use image processing algorithms to detect motion. To accomplish this, I thought that one static camera could survey the scene, and a second camera could be steered to the centre of the moving object, representing the tracking element of the Goalkeeper system.

Using a passive system such as image processing will not give me any range information. However, this should not be too much of a limitation due to the relatively low speeds of the target. If there were particularly high crossing speeds, such as a thrown tennis ball, the limitations of the system could simply be a good teaching point.

Another unnecessary but potentially useful element of the system could be to shine a laser on the tracked target, and use the spot as the target for the gun system. In this way, a handheld laser could be used instead of the automatic system, another useful demonstration opportunity.

### Manufacture

I would like the majority of the system to be manufactured from scratch, again the idea being to learn as possible and also to teach about the experience. So, I would like the hardware to be 3D-printed plastic or fabricated from laser-cut plywood. Whilst I expect the electronics to be a mixture of Raspberry Pi and Arduino, if possible I'd like to do some PCB design and fabrication.

## In summary, a challenge

Even though I've tried to keep the scope of this project limited, it's a big challenge for me. The project is the first I've attempted that needs to encompass hardware design, mechanics and software. But it's also an exciting project that I'd love to demonstrate to people. Hopefully that motivation will last as time goes by.
