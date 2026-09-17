# Teacher Notes: Session 1 - Instructions & Systems

These notes provide background, teaching prompts and possible directions for Session 1. They can also be shared with students who want to go deeper.


## Why this session exists

Students often find it surprisingly difficult to invent a simple rule. When asked to create a generative system, they tend to jump immediately toward an image, visual effect, animation or complicated piece of code.

The purpose of this session is to move further back and ask:

> **What actually happens?**

Even an instruction such as:

> Place two points and connect them.

contains many decisions.

Where are the points? Who decides? Can they overlap? What connects them? Does the line stop at the points? What happens next? Can the process repeat? When does it stop?

Formulating a rule is already a design activity.

The class should move through:

**instruction → execution → outcome → comparison → revision**

and eventually:

**human executor → computer executor**

## The instruction spectrum

Do not present rules as a simple opposition between precise and ambiguous.

Use the examples to construct a spectrum:

**specified → constrained → interpretive → poetic**

The key question is:

> **Where does the author place control, and where do they allow interpretation?**

This question will return later with randomness, parameter spaces, agents, interaction, AI prompts and generative media.

## Sol LeWitt: where is the work?

Use LeWitt to establish the relationship between:

**idea → instruction → execution**

A useful teaching strategy is to show the written instruction before the visual result.

Ask students to sketch what they think it might produce, then reveal an execution.

Questions:

* Which decisions belong to LeWitt?
* Which decisions belong to the drafter?
* Is "random" the same as "unspecified"?
* If the work is installed twice, are both results the same work?
* What remains constant across executions?

Bring several wall-drawing instructions rather than only one. Let students compare how much each one appears to determine.

Avoid presenting LeWitt simply as the "strict rules" artist. Many wall drawings deliberately give substantial responsibility to the drafter.

Useful source:

* MASS MoCA Sol LeWitt collection

## Conditional Design: designing conditions

Conditional Design changes the relationship from:

**author → instruction → executor**

to something closer to:

**rules → participants → interacting decisions → evolving outcome**

This is important because every action changes the state of the system for the next participant.

It introduces computational ideas without code:

* state
* sequence
* legal moves
* constraints
* feedback
* emergence
* stopping conditions

The important distinction is:

> **designing a composition**

versus

> **designing the conditions from which a composition can emerge**

Bring the Conditional Design book and allow students to browse it. Do not turn the entire archive into slides.

Questions:

* Does order matter?
* Can one participant make a future action impossible?
* Does the system have memory?
* Can we predict the outcome?
* Did the participants develop strategies not contained in the written rules?

## George Brecht: from image to event

Brecht is the first important expansion of the category.

With his Event Scores, an instruction no longer needs to generate a visual composition. It can generate an event, action, sound or situation.

Use *Water Yam* visually. The box of cards makes the idea of a collection of executable propositions immediately understandable.

Then concentrate on *Drip Music (Drip Event)*.

The Getty Scores Project is particularly good for teaching because it includes:

* the original score
* the *Water Yam* cards
* commentary
* examples of different performances

Rather than explain Fluxus in depth, ask students to compare realizations.

Questions:

* What remains the same?
* What changes?
* How much information is actually necessary?
* Is the performer solving a problem or interpreting a proposition?
* When does interpretation become authorship?

This is also an early bridge toward sound and time-based work later in the semester.

## Alison Knowles: the ordinary as a generative system

*Make a Salad* is useful because students immediately understand the basic action.

No specialist art knowledge is required to understand what "make a salad" means.

Yet the score can produce radically different events depending on:

* scale
* location
* ingredients
* number of participants
* available tools
* social context

The Walker article is useful to project because it contains extensive documentation from different performances.

Ask:

> **What needs to remain constant for this still to be Make a Salad?**

This is closely related to generative coding.

If a program creates thousands of different outputs, what makes them outputs of the same system?

This example also helps students understand that a simple rule is not necessarily a weak rule.

## Yoko Ono: when execution becomes imagination

Ono is useful at the end of the reference sequence because she stretches the idea of instruction furthest.

In *Grapefruit*, a score may be:

* executable
* difficult
* improbable
* poetic
* physically impossible
* primarily mental

Use the MoMA object page as the visual reference for the book itself and the Moderna Museet text for conceptual background.

The important discussion is not whether these are "real instructions".

Instead ask:

* What happens when execution is impossible?
* Does the reader still produce something?
* Can an instruction primarily produce an idea?
* Is imagining a result a form of participation?

A useful follow-up question is:

> **What would happen if we made this instruction perfectly precise?**

Often the poetic quality would disappear.

This prepares students for an important course-wide idea:

> Precision is not automatically better.

The designer chooses where precision is useful and where openness is useful.

## The five examples as a progression

I would teach them in this order:

1. **Sol LeWitt - specify**
2. **Conditional Design - constrain**
3. **George Brecht - produce an event**
4. **Alison Knowles - structure an everyday action**
5. **Yoko Ono - activate imagination**

Do not spend equal time on all five.

A possible rhythm is:

* LeWitt: 6 min
* Conditional Design: 5 min
* Brecht: 3 min
* Knowles: 3 min
* Ono: 3 min

The goal is not an art-history lecture.

The goal is to progressively destabilise the students' idea of what a rule can be.

Finish with:

> **How much should a rule determine, and how much should it leave open?**

Then move into making and executing rules.

## From one rule to a system

This is one of the most important demonstrations of the session.

Build a system live in front of the class:

> Place a point.

Ask what is missing.

Then:

> Place two points.

Then:

> Connect them.

Then add repetition.

Then add a constraint.

Then add a stopping condition.

Do not invent all the rules yourself. Ask the class what could come next.

The aim is to demonstrate:

> **Complex outcomes can emerge from simple relationships.**

Students need permission to start with something extremely simple.

## Useful vocabulary

When students are stuck, use:

* starting condition
* action
* relationship
* repetition
* variation
* constraint
* condition
* stopping rule

These are scaffolding, not requirements. A system does not need all eight.

## Common student difficulties

### "I don't know what rule to make"

Ask:

> What is one thing that can happen?

Then:

> What can it respond to?

Then:

> Can it happen again?

### The rule becomes complicated immediately

Remove rules until something interesting still happens.

### They describe a picture rather than a system

Ask:

> What could change while the rules remain the same?

### They use randomness whenever something is unspecified

Ask:

> Do you want the decision to be random, or do you want the executor to decide?

These are not the same.

### They think unexpected execution means failure

Redirect from:

> They did it wrong.

toward:

> What information did your instruction actually contain?

Unexpected results are evidence about the system.

## Human to Human

Keep the visual vocabulary constrained:

* point
* line
* circle
* rectangle
* filled area

The executor should not see the intended result and should not ask questions during the first execution.

The discomfort is useful.

When comparing the results, focus on:

* missing information
* assumptions
* interpretation
* useful ambiguity
* unnecessary ambiguity

Ask students to revise only the most consequential rules rather than rewriting everything.

## Human to Computer

Do not let the final part turn into a JavaScript lecture.

Introduce the computer as another kind of executor.

Use only a tiny p5.js vocabulary.

The important comparison is that a human may understand:

> Draw a circle near the centre.

while code forces the student to decide what "near", "centre", canvas size and circle size mean.

Avoid loops, randomness and animation. These belong in the following sessions.

## Connection to later AI work

Session 1 should return explicitly when generative AI is introduced.

Compare:

**human-readable instruction**

**p5.js code**

**AI prompt**

These are three very different relationships between author and executor.

Questions to revisit:

* Which executor interprets?
* Which fills in missing information?
* Which is deterministic?
* Where does variation come from?
* How reproducible is the result?
* How much does the author need to specify?
* Where does authorship sit?

This makes the early no-AI exercise directly relevant to the later AI part of the course.

## Sources worth keeping open during class

* MASS MoCA - Sol LeWitt wall drawings
* Conditional Design archive
* Conditional Design book
* Getty Scores Project - George Brecht / Water Yam / Drip Music
* Walker Art Center - Make a Salad
* MoMA - Yoko Ono, Grapefruit
* Moderna Museet - Grapefruit: Idea as Art

The detailed links are collected on `examples.md`.
