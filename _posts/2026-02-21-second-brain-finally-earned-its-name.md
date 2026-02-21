---
layout: post
title: '"Second Brain" Finally Earned Its Name'
comments: false
excerpt: "We had databases that couldn't think and AI that couldn't remember. Then Claude CoWork came out and something clicked."
tags:
  - AI
  - productivity

---

I'm a [productivity nerd](https://eddiesmo.com/comparing-gtd-implementations-evernote-todoist-nirvanahq-facilethings-more/). I've been maintaining a personal knowledge base and journal for years, and I've tried all the tools: Notion, Tana, Capacities, Roam Research, Obsidian.

Despite some people [calling](https://fortelabs.com/blog/basboverview/) these systems a "second brain," they were really just elaborate reference systems. I found journaling useful for thinking and tracking my day, but the evolving, interlinked database never paid dividends - it became an afterthought, not well maintained.

Then ChatGPT happened and changed how we all work. Suddenly you had a thinking partner you could throw anything at. But it couldn't remember - every conversation started from zero. Paste your context, write an elaborate prompt, get your answer, close the tab. Next time, start over.

So we had databases that couldn't think and AI that couldn't remember. Then Claude CoWork came out and something clicked - I could point it at an Obsidian vault and get both in one system.

## What's Fundamentally Different

1. **Your primary interface to the database is AI chat.** You talk to it, think out loud, ask questions. It auto-loads only the relevant context from the database and responds with your own knowledge as a foundation.
2. **Your database evolves over time,** maintained jointly by you and the AI. When context is missing or a conversation surfaces something new, I tell the AI to update the knowledge base - and it does, following rules I've defined and subject to my review via Git.

<figure class="align-center">
  <a href="#"><img src="{{ '/images/second-brain/cowork-screenshot.png' | absolute_url }}" alt="Claude CoWork interface showing the AI working with a knowledge base"></a>
</figure>

## Setup

### The Vault

The knowledge base is a folder of Markdown files - plain text, future-proof, version-controlled with Git. I use Obsidian to browse and read, and Cursor when editing the AI rules, but the files are just files. Any editor works.

The structure is up to you. Mine has areas of life (health, career, interests), time-bound projects, evergreen notes, and a daily journal that interlinks to everything else. Use whatever system works for you.

<div class="notice--info" markdown="1">
I've put together a [demo repo](https://github.com/eddiesmo/second-brain-demo) you can clone and adapt.
</div>

What makes it a "second brain" rather than a fancy notes folder is a thin layer of instruction files on top. A top-level `CLAUDE.md` tells the AI what the vault is, how it's organized, and what conventions to follow. Deeper `CONTEXT.md` files give it background on specific areas and projects - so it loads only what's relevant, not everything. Rules and skills teach it your workflows: how to write, what to update, when to ask.

### The Chat

I talk to the AI via Claude CoWork or Claude Code. It operates directly on the repository. You just talk to it like you would to ChatGPT, except you barely need to provide any context. It does the rest:

1. Creates a to-do list, often searching or researching first
2. Replies in the chat *and* creates or updates files directly in the vault

**Braindumping on the go.** Using a speech-to-text app like Typeless or WisprFlow, I go for a walk and ramble my thoughts into Claude. It drafts a journal entry, we go back and forth on it, and by the time I'm back at my desk there's a polished entry waiting in the right folder - interlinked to related notes, with my thinking sharpened in a way that feels like I actually worked through the idea.

**Working through hard decisions.** I can throw my most difficult questions at it and be genuinely surprised by the quality. With all the context it loads from the vault - often more than I myself remember - Claude really steps up. It doesn't just have the relevant information for the decision; it also draws on recent journal entries and pulls unexpected connections to my mood, motivation, and other goals. I've been surprised more than once at the kind of insights it surfaces.

## Open Questions

With all the tools improving so quickly, I'm sure this is far from the endgame. But I'm also sure this is the right direction, and that the database I'm growing will be the foundation of whatever comes next. It's thrilling to feel the double improvement - both the growing knowledge base and the rapidly improving LLMs and tools around it.

Some things I'm wondering about:

- **GTD integration** - how to combine this with task management
- **Multiplayer** - how this extends to team environments and shared knowledge bases
- **Commercial solutions** - I'm watching how knowledge management products adapt to these new workflows. My concern is lock-in. With AI tools improving daily, I want control over my files and the freedom to use whatever interface comes next.

For now, the system works - and it gets better every time I use it. That's the whole point.
