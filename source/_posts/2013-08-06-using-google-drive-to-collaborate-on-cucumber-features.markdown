---
layout: post
title: "using google drive to collaborate on cucumber features"
date: 2013-08-06 03:35
comments: true
categories: [Scrum, Cucumber]
---

I have been working as a scrum master with remote teams for 2.5 years and during that time I have deviated a bit from textbook Scrum process. If your working with remote teams, especially if you have members of your team who speak different languages you should be familiar with the cost of miscommunication.

<!-- more -->

Cucumber
--------

There are a few alternatives when it comes to integration testing your app including the built in Rails integrations tests. I prefer being able to write my integration tests in plain English before writing any code. When I first started with Rails, I was also reading a lot of marketing material around personae and user journeys. The core idea is to decide who your ideal customers are and what they want to achieve. Asking these questions around **how** and **why** results in much better web apps.

I find that asking **why** is a core part of writing cucumber features, in a lot of situations, feature requests (tasks) are handed down to programmers who don't delve deeply enough into why a feature is needed. This is often based on project managers or clients requesting things without themselves asking why its needed. Its also natural to make assumptions so I find writing a cucumber outline really helps me to think things through. On many occasions questions are revealed that lead to better ideas and simpler implementations.

Don't do planning meetings
--------------------------

My experience working with remote teams is that the traditional planning meeting once per iteration has limited value. If you have multiple remote locations and language barriers, having everyone in a campfire room or Skype chat, can be very painful. I also find thats its very easy for people to forget the points discussed.

Estimate based on complexity
----------------------------

Instead of planning meetings we do ad hoc estimation meetings. In these meetings we ignore implementation details or discussions about which gem to use, we simply focus on how complex the tasks sound. Normally we spend about 10-15 minutes on estimation per week.

Plan with cucumber
------------------

Normally a developer will pick up a task and in an ideal world, they would write a cucumber outline before starting to code. At this point they should then proceed with the WHY cycle and try and determine if the task can be de-scoped.

We have taken this in a slightly different direction by turning cucumber outline writing into our planning meetings. We are using Google Drive which is pretty awesome. We are doing plan per feature rather than one big plan it all type meeting.

* Collaborative editing - The team can all see the outline taking shape in real time. Readability and clarity of purpose is a real benefit to this.

* Inline chat - Being able to chat inside a google doc (in the margins) is really pretty cool.

* Native apps - the app for the iPhone and iPad work amazingly well. On a few occasions I have been shopping and at the same time writing an outline. Its really enjoyable to use.

We normally start each document with a Q+A session, sometimes these are copied from campfire or Skype discussions. In short the google doc becomes a dumping ground for any ideas, edge cases, whatever. We include our QA in the process so they know what is integration tested and they know what to expect from the feature when they test it manually.

I normally spend a lot of time discussing ideas with the client, I can dump these conversations in the doc for developer reference.

Does it work
------------

It's working very well for us. Rework is massively reduced, our cucumber outlines are very readable meaning new developers have a much better source of documentation to reference. We are more Agile, complex features are identified before we start to code.

Planning is focused, we just write cucumber outlines for the tasks planned in the next iteration, although we spend a few hours a week on cucumber outlines, when a developer starts a feature, they can just copy paste the scenarios and start implementing the steps.

Because the user journey is designed outside of the developer flow, managers, BA's and clients can talk about UX in an open ended way. Developers don't start a task in PT unless it has an approved cucumber outline.

Pivotal Tracker
---------------

I have been a PT devotee for quite a few years now, its light weight and has just enough features to keep me happy. Although its got commenting its not got the formatting and scope of a google document. Its great for light chat, but if the feature is complex and you want pages and pages of text, its not that easy to read. PT is designed to be light weight and I would not change that.

Linking PT to Google Drive
--------------------------

This is pretty easy to do, both Google Drive and PT have good search, so all thats required is to put the PT task number into the google doc file name, it's also easy to put a link to the google doc inside PT.

![Google doc with PT task number][google_doc]

[google_doc]: /images/posts/google_doc.png

That filename reveals a convention we use for naming features in PT.

_usba2 = User should be able to_

We try and focus as much as possible on naming features in terms of user objectives. This leads to a lot of developer freedom.

The future
----------

We have allocated a lot of Slack time to making this process easier. You might be familiar with some of the PT / Git workflow gems available. Some of these allow you to control PT from the command line and allow git commits to be linked to PT tasks. We have some ideas on this front to integrate Google Drive with PT. The idea is that when you start a PT task from the command line it will automatically download the cucumber outline from google drive and insert it into a file.

Google Drive is stateless
-------------------------

One pain with Google Drive is that documents are stateless, unlike PT where a task goes through a flow until its marked **accepted** we need a new solution to organise our docs. Currently we are using folders to solve this. This is what ours looks like:

![My google drive][google_drive_folders]

[google_drive_folders]: /images/posts/google_drive_folders.png  "Story state using folders"

Since both PT and google drive have APIs we might be able to synchronise activity between PT and Drive more with a bit of dev effort.

Business analysts
-----------------

If you work with a BA or there is a real interest from the business in the user journey then Google Drive might be something to investigate.


