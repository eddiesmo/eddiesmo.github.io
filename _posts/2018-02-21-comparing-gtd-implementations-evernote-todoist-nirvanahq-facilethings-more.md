---
layout: post
title: Comparing Getting Things Done (GTD) Implementations in Evernote, Todoist, NirvanaHQ, FacileThings and more
comments: false
excerpt: "When I started using GTD, the best implementation I found was in Evernote. I’ve used and refined it for years, until last year I finally decided it’s time to switch. Surely a better implementation must exist by now."
tags:
  - getting things done
  - 

---

{% include toc %}


If you're unfamiliar with Getting Things Done, I strongly urge you to go read the book, it's a life changer. I do not intend to repeat the contents here, but I will include some nice variable-length summaries I've found and enjoyed:

- [GTD in 15 minutes](https://hamberg.no/gtd/)
- [YouTube animated book summary [8 min]](https://www.youtube.com/watch?v=gCswMsONkwY)
- [Wiki book summary](http://www.wikisummaries.org/wiki/Getting_Things_Done:_The_Art_of_Stress-Free_Productivity)
- [Lifehacker Primer on GTD](https://lifehacker.com/productivity-101-a-primer-to-the-getting-things-done-1551880955)

# Introduction

Getting Things Done is one of those very rare books that *changed my life*.
Before reading it in 2014 I considered myself a smart and driven person, but also unreliable, irresponsible and chaotic. I would pick up and drop projects on a whim, forget tasks that I promised to do, arrive late to everything and generally I just felt unproductive and stressed. The trust between present-me and future-me was pretty low.

It's not a perfect book (I gave it a 4/5 on Goodreads), but the abstract concepts behind it are so powerful that I feel like it gave me a superpower. Having been published almost 20 years ago it is still the leading method of personal productivity that I'm aware of. While originally it was implemented with physical files, folders and papers, it has since been transformed by many practitioners to accommodate to the digital age.

When I started using GTD, the best implementation I found was in Evernote. It was called “The secret weapon” and it worked well - I’ve used and refined it for years, until last year I finally decided it’s time to switch. Surely a better implementation must exist by now.

After taking a couple of months to try different software solutions, I've settled on using **NirvanaHQ**. In the next section I explain why.

# Bottom line

For those who just want a straight answer, NirvanaHQ is my winner. After sticking with it for months, I'm still very happy. I summarize the comparison below:

**Evernote:** my first GTD implementation. Used it in 2014-2018 and it completely worked. Clunky to set up and clunky to use, but versatile enough to deliver a full GTD experience. In my opinion it was the best option until recent years.

**Todoist:** a well designed and implemented general task-management app. Requires a lot of tinkering to fit to the GTD system and then it's a proper  solution. I love how responsive and intuitive the app is and that it has many third party integrations. Currently my second choice.

**NirvanaHQ [winner]:** finds a great balance between true GTD implementation and a light, well designed modern service for web and mobile. It's not perfect (I am sorely missing integrations with outside services such as calendar or IFTTT/Zapier and support for task images / attachments), but it really achieves the GTD vision simply and beautifully. My current choice.

**FacileThings:** the most true, hard-core implementation of GTD I've seen and a great tool to introduce newcomers to the system with a guided experience. The only tool that has built in consideration of your purpose, vision, goals, areas of responsibility and even formalized a weekly review process. Too bad the UX is not so well designed and requires a lot of clicks to get anything done, and perhaps a bit too restrictive in doing GTD "the right way".

I've also tried other apps like **AnyDo**, **Wunderlist** and **Remember The Milk** but didn't find them to fit well with GTD.

If you're interested in setting up a GTD implementation for a non GTD-native app like Evernote or Todoist, read on...

# In depth discussion

### What is required to implement GTD?

As far as I can see, to implement GTD you need two things:

1. Mutually exclusive folders/labels to represent **task status**:
 [Inbox / Now / Next / Someday-Maybe / Waiting-Delegated / Complete].
This is trivial: I need to be able to move a task from one status to another and have it erase the previous one automatically (otherwise, when I label something as next I'd have to also remove the label soon).
2. Concurrent labels to represent **context**:
- *What:* properties of your tasks such as: priority, low/high energy, estimated time and so on. They can also be keywords such as: health, finance, family and so on.
- *Where:* places where you're likely to do tasks.
- *Who:* separate tags for people you frequently work with or delegate tasks to.

The context labels allow me to figure out what to do next that fits my context. For example when I'm driving, need to fill 10 minutes or am in the mood to do something specific.

If you can make these two requirements work, you've got yourself a basic GTD system and the rest is details (which can sometimes still be very important!).

Further considerations:
- Separate work and life tasks easily. 
- Have useful reminders that pop up at the right time, in the right context, in the right location.
- Integrations with other services (such as your calendar).
- Great UX and a snappy multi-platform experience. 



### Evernote
My first GTD implementation. Used it in 2014-2018 and it completely worked. Clunky to set up and clunky to use, but versatile enough to deliver a full GTD experience. In my opinion it was the best option until recent years.

#### Implementation

The best implementation of GTD that I've seen for Evernote is [The Secret Weapon](https://thesecretweapon.org/). The only thing I strongly object to is their decision to implement task status as tags, under a .when label (see their setup page).
In Evernote, I think task status must be implemented using the notebooks, since they are the only mutually exclusive kind of tag (reasoning given [above](#what-is-required-to-implement-gtd)).
Below is a screenshot of my own setup which has worked for me for years. Note the separation of work and life into two notebook stacks. Task status switches are very easy to manage.

<figure class="align-center">
  <a href="#"><img src="{{ '/images/gtd/eddie-gtd-evernote.png' | absolute_url }}" alt=""></a>
  <figcaption>My Evernote GTD implementation. Left: task status as notebooks. Right: context as nested tags.</figcaption>
</figure> 

#### Pros
1. Super easy to capture tasks, ideas and information. Evernote implemented a great capturing tool on android by creating a 1-click widget to capture text, photos or voice. Everything goes into the inbox to be processed later.
2. Extremely flexible. Using notebooks and tags you can set up your system any way that you want. Tags have infinite hierarchy.

#### Cons
1. Not GTD-native. By that I mean that while Evernote is versatile enough to implement GTD, it wasn't built with GTD first in mind. The result is a somewhat clunky daily experience. For example:
  - [ ] Tasks are just Evernote notes, which don't have standard task properties like energy levels, time estimation or the ability to "tick" a box when done in a satisfying manner.
  - Reminders in Evernote are weak and it is hard to define and properly follow self-imposed due dates.
2. Two GTD notebook stacks are required to separate work and life tasks. Or at least that's the best separation I could think of.



### Todoist
A well designed and implemented general task-management app. Requires a lot of tinkering to fit to the GTD system and then it's a proper solution. I love how responsive and intuitive the app is and that it has many third party integrations. In my opinion even after proper setup it's second to NiravanaHQ, but for non-GTD-purists it might be a winner.


#### Implementation 

The setup in one picture:

<figure class="align-center">
  <a href="#"><img src="{{ '/images/gtd/eddie-gtd-todoist.png' | absolute_url }}" alt=""></a>
  <figcaption>My Todoist GTD implementation. Left to right: Favorites, Projects, Labels, Filters.</figcaption>
</figure> 

The main problem with implementing GTD on Todoist is that this software is oriented around due dates and there is no clear way to implement task status. This could be solved by either having a set of mutually exclusive labels (for task status) or simply nested labels (for projects, which would free up the Todoist projects pane for task status purposes). Unfortunately both features are missing, so I'm facing a dilemma:

- If I use the projects tab for task status, then I have to implement my actual projects as labels, which sucks because Todoist labels are not nested and generally not first class citizens.

- If I use labels for task status, they are not mutually exclusive which is one of the two requirements [above](#what-is-required-to-implement-gtd).

**How to solve this?** Interestingly, I found a way around this limitation with the use of filters: give each task-status a label.

For each task-status create a filter which shows only tasks for which that status is the highest priority.
Add the filters to favorites and then view the task statuses from there.

As an example, say I have the task "buy milk". 
At first I add the label *Soon* to it. Then at some point the task becomes relevant and I add the label *Next* to it. The filter for *Next* is set up in such a way that it shows everything with label *Next*, so the task will be seen under it. But! The filter for *Soon* is set up so that tasks which belong also to *Next* do not appear under it, and so the task is effectively gone from this view. 

To define the filter simply enter: `Soon & !Next` which translates to: "Show me tasks which belong to Soon and don't belong to Next". 

Naturally I setup the other task-status the same way.

#### Pros
1. Full of integrations with other services
1. A very smooth experience both on web and mobile
1. Powerful reminders and repeating tasks

#### Cons 
1. Not GTD-native and not trivial to set up proper GTD even when trying. And to be honest, even after proper set up I was still missing some critical GTD features like assigning a contact person to a task (it's possible to implement contacts as labels, but since there are is no nesting with Todoist labels it becomes a mess).
1. I don't really get the purpose of the karma system (scores your productivity).




### NirvanaHQ [winner]
Nirvana Finds a great balance between true GTD implementation and a light, well designed modern service for web and mobile. It's not perfect (I am sorely missing integrations with outside services such as calendar or IFTTT/Zapier and support for task images / attachments), but it really achieves the GTD vision simply and beautifully. My current choice.

#### Pros
1. GTD-native. Easy to manipulate and process the tasks.
1. Intuitive UX and a smooth experience across web and mobile.
1. Using *Areas*, very easy to separate work and life tasks.
1. Overall, strikes a great balance between GTD purity and great UX.

#### Cons
1. No integrations with other services such as calendar.
1. No support for attachments of any kind. This service is only text-based for now.
1. Repeating tasks do not support countdown from the time your finished the previous iteration of the task.
1. Task capturing on mobile is weak (requires opening the app and then a long press on "+"). This is solved by adding an [IFTTT note widget](https://ifttt.com/applets/DPswmWqz-send-to-nirvana-inbox?term=nirvana) which sends an email to my Nirvana inbox.



### FacileThings
The truest, most hard-core implementation of GTD I've seen. It is the only tool that has built in consideration of your purpose, vision, goals, areas of responsibility and it even formalized the weekly review process. Too bad the UX is not so well designed and requires a lot of clicks to get anything done, and perhaps a bit too restrictive in doing GTD "the right way".

One thing I've noticed about FacileThings is that it's a great platform for introducing people to the GTD method. Some of my friends who were not that interested in reading the book were happy to just watch a youtube summary of it and then try FacileThings, which provided a guided, handheld GTD experience. As their free trial ended, some of these friends decided to continue with GTD, but not all of them stayed with FacileThings.

#### Pros
1. A great, very true implementation of GTD. I've actually recommended this service to friends as an introduction to the method instead of the book - it's more interactive and forces you to work right.
1. The only implementation I've seen that incorporates higher GTD concepts such as the weekly review, areas of responsibility, Vision, life goals, etc.

#### Cons
1. Clunky UX. It's too hard to manipulate tasks and get all their parameters right.
1. Mobile experience is not good.
1. Not flexible. You can't do shortcuts that are against the pure GTD way. For example: 
- you can't add a task to the inbox and immediately process it. It goes into a processing queue which means that I only get to fill out the details when I've already left the current context.

