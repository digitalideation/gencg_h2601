# Teacher Notes: Research & References

This annex is a practical research workshop for the final-project phase. It complements the existing [process journal guide](./journal.md) rather than introducing a new documentation system.

The priority is to help students move from **finding something interesting** to **understanding it, connecting it to their project and deciding what to try**.

## Why this workshop?

Students already document code and screenshots, but collecting artistic references and using them in their thinking is less automatic. We have mentioned research throughout the course. This time we make that process visible.

I would avoid turning it into a lecture on research methodology or a long Obsidian tutorial. A live demonstration with real decisions and small checkpoints should be more useful.

The key thread is:

**Question → Discover → Collect → Connect → Test → Reflect**

The live demonstration shows how to research. The student annex gives them a template to document it. There is no need to write an entire journal entry in front of the class.

## Two examples to open with

### Vera Molnár: thinking on paper

Students already know her notebooks from the journal guide:

- [Journal, part 1](../../assets/pdf/vera_journal_01.pdf)
- [Journal, part 2](../../assets/pdf/vera_journal_02.pdf)

Use these briefly, as a reminder that sketches, repeated experiments and small variations are meaningful documentation. Do not insist that students reproduce her drawing practice. Their working material may be sketches, code, screenshots or media.

Ask: **What can these records tell us about an idea that a finished artwork cannot?**

### Zach Lieberman: research and decisions

Use the actual article: [Más Que la Cara: Overview (2017)](https://zachlieberman.medium.com/m%C3%A1s-que-la-cara-overview-48331a0202c0).

The article is a detailed retrospective of a collaborative public art installation in Houston. It is not a model for how long a student journal entry should be. It is useful because the documentation connects different parts of the process.

Give students four things to find in the introduction and the **Design process** section. Some examples you can draw on during discussion:

| Look for | Possible finding in the article |
| --- | --- |
| **Artistic reference** | Bruno Munari's minimal representations of faces; traditions of masks; poster graphics |
| **Experiment** | Cardboard-mask workshops; Illustrator sketches exported as SVG and tested with a moving face |
| **Problem** | How to make face augmentation feel different from a novelty filter; how to make the graphics legible over the face |
| **Decision** | Develop the visual direction as a **living poster**, with graphic compositions rather than conventional filter effects |

Other valid answers are possible. Students should be able to **point to evidence** in the article rather than guess what happened.

If some students are interested in implementation, the later technical section explains the use of **paper.js** for graphics and **openFrameworks** for tracking, as well as problems with lighting and face tracking. This is optional: don't turn the discussion into an explanation of those tools.

The question I would ask afterwards is: **When did a reference, observation or problem actually influence what the team made?**

## Your live research demonstration (about 20 min)

Choose a theme that relates to generative coding but leaves room for discovery. One possible starting question:

> How can simple geometric rules create the impression of growth or organic behaviour?

I would investigate it live, even if the search is a little messy. That is part of the point: students should see how you choose between results, change search terms and follow sources.

A possible rhythm:

1. **Define the question (3 min).** Narrow the theme until you know what you want to investigate. What would count as a useful finding?
2. **Search and follow leads (6 min).** Try a few searches for artistic projects, then one for a technique. Open a promising result and follow through to the artist or project's original page.
3. **Read the reference (5 min).** What is the work actually doing? Can you find process information, code, sketches or the creator's account of how it was made? Identify artist, title, year and source.
4. **Make a connection (4 min).** Describe one formal or behavioural rule you noticed and how it could inform a different experiment in p5.js.
5. **Formulate a next step (2 min).** State a simple test you could make, such as a branching system with one controlled parameter.

You do **not** have to write the journal entry live. You can end by pointing to the short copyable template on the annex page, showing which information your search produced.

If the first search produces weak results, say why, adjust it and continue. That is a useful demonstration of research judgment. It may help to have one original project page bookmarked as a fallback if the internet is slow.

Distinguish between an **artistic reference**, which can influence ideas or visual language, and a **technical reference**, which helps implement a specific behaviour. Students can use both without treating them as interchangeable.

## A possible 150-minute rhythm

| Duration | Activity | Checkpoint |
| --- | --- | --- |
| 10 min | Introduce Molnár and Lieberman | Why document the process? |
| 15 min | Students investigate Lieberman's article | Identify reference, experiment, problem, decision |
| 10 min | Compare findings together | Where did research affect a decision? |
| 20 min | Live research demonstration | One question, one source, one possible experiment |
| 10 min | Break | |
| 25 min | Individual research sprint | Find one or two sources |
| 20 min | Collect and annotate in Obsidian | Explain why the references matter |
| 30 min | Test something or plan a concrete test | Make a decision informed by research |
| 10 min | Closing | One reference, one connection, one next step |
| **150 min** | | |

These are suggested times, not a rigid sequence. The useful constraint is that independent work has clear purposes and stops for a few meaningful checkpoints.

## Facilitation: questions worth asking

As students research, walk around and ask:

- What question are you trying to answer?
- Is this the original project source, or someone's repost?
- What about this reference is relevant to your project?
- Do you know anything about the method, or only the appearance?
- What will you test differently because you found this?
- Can you explain that in two sentences in your journal?

Try not to recommend the same artists to everybody. If they are stuck, help them sharpen their question before suggesting sources.

If students find ten images quickly, ask them to select **one or two worth investigating**. More collected content is not necessarily better research.

If they keep writing without testing anything, ask them to sketch a variation or formulate a specific experiment. If they start coding and forget the journal, bring them back to the reference and ask what actually influenced their decisions.

## Documentation without extra bureaucracy

Students already have four dimensions in their journal: **exploration, influences and references, algorithmic thinking, critical reflection**. We are reinforcing the references part, not introducing new assessed categories or another submission.

The annex provides a small reference template with a source, observation, connection and possible experiment. It is optional scaffolding.

Because their journals are public, remind them to credit sources and only upload images they have the right to reproduce. When unsure, a link to the artwork's original page is enough. For AI-assisted searches, verify the artist and the work from reliable sources rather than citing an AI summary as evidence.

## Closing

I would avoid full presentations. Ask one or two students to share a useful discovery, then have everyone put a short note in the journal:

**I found ..., this matters because ..., and next I will try ... .**

An unfinished experiment is fine, as long as the next step is concrete.

The broader message: **research isn't an archive of inspiring images. It is part of how we make creative decisions.**

→ [Student annex](./research-and-references.md)
