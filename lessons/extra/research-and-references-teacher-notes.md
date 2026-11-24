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

**Starting question: How can typography become interactive?**

This is a good theme because everyone knows what letters do, but creative coding lets us investigate what they might **do differently**. Typography can respond to movement, mouse position, sound or other inputs. The research should help us discover possibilities before choosing one.

I would demonstrate the process live, including how I select results, investigate the source and change direction when a search is unhelpful. I would not try to build a sketch or write a full journal entry in front of the class.

### 1. Start with the question (2 min)

Write **How can typography become interactive?** on the board.

Ask what interaction might mean here. Do the letters move? Change shape? Respond to the cursor? We do not need to settle on an outcome yet.

### 2. Search for artistic references (6 min)

Start with a few searches, for example:

- `interactive typography art`
- `generative typography creative coding`
- `experimental interactive typography`

Compare a couple of results and follow an interesting one to the **artist's original project page**, rather than stopping at image results or reposts.

Ask: Who made it? What actually changes? What triggers the change? Why does this particular interaction interest us?

### 3. Investigate one project (5 min)

Look beyond the final image or video. Can we find a project description, sketches, code or an explanation of the process?

Distinguish **what we observe** from **what we know** about how it was made. Note the artist, work title, year if available and original source.

A suitable fallback project is [Selina Kehuan Wu's Magnetic Type Maker](https://kehuan.work/Magnetic-Type-Maker-1). Keep it bookmarked, but try to let the live search lead somewhere naturally.

### 4. Connect artistic and technical research (5 min)

Take one observation and turn it into something we might investigate with code.

For instance, if the reference shows letters responding to the cursor, we could search for:

- `p5.js interactive text`
- `p5.js mouse distance`
- `p5.js moving letters`

Now we have two kinds of research: an **artistic reference** that suggests an approach and a **technical reference** that might help us test it.

A possible experiment is: *Can I make the letters in a word move apart when the mouse approaches them?*

The goal is not to reproduce the artwork. It is to explore one principle in our own way.

### 5. Formulate a next step (2 min)

Summarise the discoveries in four short points:

- **Reference:** Who made the project, and where can we find the source?
- **Observation:** What is interesting about its interaction?
- **Connection:** What could matter for a project of our own?
- **Experiment:** What is one small test we could make in p5.js?

Point students to the reference template in the [student annex](./research-and-references.md). No need to open Obsidian and compose the entire entry live.

### Keep in mind

The search does not have to go smoothly. Explaining why a result is irrelevant, changing keywords or following a better source demonstrates research judgment.

Keep one or two original project pages bookmarked in case the search or network fails. The aim is to demonstrate **how to move from a question to a reference, from an observation to a technical question, and from there to an experiment**, not to find a perfect example.

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
