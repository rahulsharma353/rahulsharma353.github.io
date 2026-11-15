---
layout: post
title: "Why I'm Building PM in the Loop (and My First Agent Skill)"
pillar: Agent skills for PM work
excerpt_text: "Most AI-for-PM content is either strategy decks with no hands, or engineering tutorials with no PM context. Here's the middle ground I wanted to exist — plus the prompt I use to turn messy research into a structured findings doc."
---

I've spent over a decade as a PM across Cloudera and Dell, most recently running a data services platform, AI inference products, and partner ecosystem work. Somewhere in the last two years, the job changed under my feet. It's not enough anymore to have a point of view on AI — you need to actually be able to build with it. Wire up an agent, write a prompt that survives contact with real data, know when to trust the output and when not to.

Most AI-for-PM content I read falls into one of two buckets: high-level strategy decks with no hands, or engineering tutorials that assume you already live in a terminal. I wanted something in between — a place where I write down the actual skills I'm building, week by week, as I build them. Equal parts teaching and notes-to-self.

That's what this site is. One post a week. Every post ends with something you can copy and use today.

### The first skill: turning messy research into a synthesized insight doc

Here's a task every PM has done badly at least once: you've got a stack of user interview notes, some support tickets, maybe a survey export, and you need a structured findings doc by end of day. The old way is skimming everything twice and writing bullet points from memory — which quietly drops the outlier finding that actually mattered.

Here's the prompt I use to have an AI agent do the first pass, so my time goes to judgment instead of transcription:

```
You are helping me synthesize raw user research into a structured findings doc.

Input: [paste interview notes / ticket exports / survey responses]

Do the following:
1. Extract every distinct theme mentioned, however small.
2. For each theme, count how many sources mentioned it and quote the
   sharpest verbatim example.
3. Rank themes by (frequency x severity), not just frequency — a theme
   mentioned once by an enterprise customer about a blocking issue outranks
   a theme mentioned five times as a minor annoyance.
4. Flag anything that contradicts our current roadmap assumptions.
5. Output as a table: Theme | Frequency | Severity | Example quote |
   Suggested action.

Do not soften or round up sentiment. If the data is thin on a theme, say so
instead of extrapolating.
```

What this buys you: a first draft in minutes instead of an afternoon, with the tedious extraction done consistently. What it doesn't buy you: judgment on what's actually worth acting on. I still read every quote myself before it goes near a roadmap doc — the agent is a very fast intern, not a replacement for having sat in the interviews.

Two things I've learned running this repeatedly:

**Severity beats frequency, and you have to say so explicitly.** Left alone, these tools default to "most mentioned = most important," which is exactly backwards for the finding that should scare you.

**Ask it to flag contradictions to your existing beliefs, not just confirm them.** Without that instruction, synthesis tools tend to hand you back a fancier version of what you already thought going in.

### What's next

Next week: building a weekly metrics review agent — the prompt and workflow I use to turn a raw metrics dump into a scorecard with recommended actions before Monday standup.

If you're a PM building with AI agents and want to compare notes, this is exactly the kind of thing I want to hear about. See you next week.
