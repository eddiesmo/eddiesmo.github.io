---
layout: post
title: Comparing Getting Things Done (GTD) implementations in Evernote, Todoist, NirvanaHQ, FacileThings and more
comments: true
tags:
  - getting things done
  - 

---

If you're unfamiliar with Getting Things Done, I strongly urge you to go read the book, it's a life changer. I do not intend to repeat the contents here, but I will include some nice variable-length summaries I've found and enjoyed:

- GTD in 15 minutes
- YouTube animated book summary [8 min]
- Wiki book summary
- Lifehacker Primer on GTD

# Introduction

Getting Things Done is one of those very rare books that changed my life.
Before reading it in 2014 I considered myself a smart and driven person, but also unreliable, irresponsible and chaotic. I would pick up and drop projects on a whim, forget tasks that I promised to do, arrive late to everything and generally I just felt unproductive and stressed. The trust between present-me and future-me was at pretty low levels.

GTD isn't a perfect book (I gave it a 4/5 on Goodreads), but the abstract concepts behind it are so powerful that I feel like it gave me a superpower. It also stood the test of time and is still a leading method of personal productivity today. While originally it has been implemented with physical files, folders and papers, it has since been transformed by many of its practitioners to fit the digital age.

Back in 2014, the best implementation that I have found was in Evernote. It was called "The secret weapon", and it worked great! I've used and refined it for years, until last year I finally decided it's time to move on - surely a better implementation must exist today?
After taking a couple of months to try different software solutions, I've settled on using NirvanaHQ. In the next section I explain why.

# Comparison

These are the products I've tried and my thoughts on them:
**Evernote:** my first GTD implementation. Used it in 2014-2018 and it completely worked. Clunky to set up and clunky to use, but versatile enough to deliver a full GTD experience. In my opinion it was the best option until recent years.

**Todoist:** a well designed and implemented general task-management app. Requires a lot of tinkering to fit to the GTD system and then it's a sufficient solution. I love how responsive and intuitive the app is and that it has many third party integrations. Currently my second choice,

**NirvanaHQ [winner]:** finds a great balance between true GTD implementation and a light, well designed modern service for web and mobile. It's not perfect (I am sorely missing integrations with outside services such as calendar or IFTTT/Zapier and support for task images / attachments), but it really achieves the GTD vision simply and beautifully. My current choice.

**FacileThings:** the most true, hard-core implementation of GTD I've seen and a great tool to introduce newcomers to the system with a guided experience. The only tool that has built in consideration of your purpose, vision, goals, areas of responsibility and even formalized a weekly review process. Too bad the UX is not so well designed and requires a lot of clicks to get anything done, and perhaps a bit too restrictive in doing GTD "the right way".

I've also tried other apps like **AnyDo**, **Wunderlist** and **Remember The Milk** but didn't find a them to fit as well with GTD.

If you're interested in setting up a GTD implementation for a non GTD-native app like Evernote or Todoist, read on...

# GTD implementation: Two requirements

As far as I'm concerned, to implement GTD you need two things:

Mutually exclusive folders/labels to represent task status:
 [Inbox / Now / Next / Someday-Maybe / Waiting-Delegated / Complete].
This is trivial: I need to be able to move a task from one status to another and have it erase the previous one automatically (otherwise, when I label something as next I'd have to also remove the label soon).
Concurrent labels to represent context:
What: properties of your tasks such as priority, low/high energy, estimated time and so on. It can also be topics and areas such as health, finance, family and so on.
Where: places where you're likely to do tasks.
Who: separate tags for people you frequently work with or delegate tasks to.
If you can make these two requirements work, you've got yourself a basic GTD system and the rest is details (though I admit, sometimes very important).
Implementing GTD in Evernote
The best implementation of GTD that I've seen for Evernote is The Secret Weapon. The only thing I strongly object to is their decision to implement task status as tags, under a .when label (see their setup page).
In Evernote, I think task status must be implemented using the notebooks, since they are the only mutually exclusive kind of tag (reasoning given above).
Below is a screenshot of my own setup which has worked for me for years. Note the separation of work and life into two notebook stacks. Task status switches are very easy to manage.
My Evernote GTD implementation. Left: task status as notebooks. Right: context as nested tags.
So, what was missing? Why did I want to move away from this trusted, tried and tested system?
Simple - Evernote is not GTD-native, and by that I mean that while Evernote is versatile enough to implement GTD, it wasn't built with GTD in mind first. The result is a somewhat clunky daily experience. Some examples:
Tasks are just Evernote notes, which don't have standard task properties like energy levels, time estimation or even the ability to "tick" a box when done in a satisfying manner.
Reminders in Evernote are weak and it is hard to define and properly follow self-imposed due dates.
Two GTD notebook stacks are required to separate work and life tasks.
Implementing GTD in Todoist
Todoist was my first attempt at an upgrade after
My setup in one picture:
My Todoist GTD implementation. Left to right: Favorites, Projects, Labels, Filters.
The main problem with implementing GTD on Todoist is that this software is oriented around due dates and there is no clear way to implement task status. This could be solved by either having a set of mutually exclusive labels (for task status) or simply nested labels (for projects, which would free up the Todoist projects pane for task status purposes). Unfortunately both features are missing, so I'm facing a dilemma:
If I use the projects tab for task status, then I have to implement my actual projects as labels in Todoist, which sucks because the labels are not nested.
If I use labels for task status, they are not mutually exclusive which is one of the two requirements above.
How to solve this? Interestingly, I found a way around this limitation with the use of filters:
Give each task-status a label.
For each task-status create a filter which shows only tasks for which that status is the highest priority.
Add the filters to favorites and then view the task statuses from there.
As an example: Say I have task "buy milk". At first I add the label Soon to it. Then at some point the task becomes relevant and I add the label Next to it. The filter for Next is set up in such a way that it shows everything with label Next, so the task will be seen under it. But! The filter for Soon is set up so that tasks which belong also to Next do not appear under it, and so the task is effectively gone from this view. To define the filter simply enter:
Soon & !Next
Which translates to:
"Show me tasks which belong to Soon and don't belong to Next".
Naturally I setup the other task-statuses the same way.
