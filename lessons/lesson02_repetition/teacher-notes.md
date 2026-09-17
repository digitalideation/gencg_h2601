# Teacher Notes: Session 2 - Repetition & Variation

These notes provide background, teaching prompts and possible directions for Session 2. They can also be shared with anyone who wants to go deeper.

- [Why this session exists](#why-this-session-exists)
- [From repetition to variation](#from-repetition-to-variation)
- [Vera Molnár: order and interruption](#vera-molnár-order-and-interruption)
- [Truchet tiles: local states, global patterns](#truchet-tiles-local-states-global-patterns)
- [10 PRINT: a tiny rule with large consequences](#10-print-a-tiny-rule-with-large-consequences)
- [Generative Design: reading systems through code](#generative-design-reading-systems-through-code)
- [The examples as a progression](#the-examples-as-a-progression)
- [From one mark to a field](#from-one-mark-to-a-field)
- [Variation is not randomness](#variation-is-not-randomness)
  - [Systematic variation](#systematic-variation)
  - [Alternation](#alternation)
  - [Conditional variation](#conditional-variation)
  - [Probabilistic variation](#probabilistic-variation)
- [Breaking the pattern](#breaking-the-pattern)
- [Useful vocabulary](#useful-vocabulary)
- [Common difficulties](#common-difficulties)
  - [The system becomes complicated immediately](#the-system-becomes-complicated-immediately)
  - [Randomness is added everywhere](#randomness-is-added-everywhere)
  - [Nested loops become abstract](#nested-loops-become-abstract)
  - [The image is copied instead of the system](#the-image-is-copied-instead-of-the-system)
  - [Too many variables change at once](#too-many-variables-change-at-once)
- [Repetition in code](#repetition-in-code)
- [Connection to later sessions](#connection-to-later-sessions)
- [Connection to later AI work](#connection-to-later-ai-work)
- [Sources worth keeping open during class](#sources-worth-keeping-open-during-class)

## Why this session exists

Session 1 introduced the idea that a generative work can begin with a rule rather than an image.  
Session 2 asks what happens when that rule is executed repeatedly.  
The session should move through:

**unit → repetition → variation → interruption → comparison**

The central proposition is:

> **Repetition creates structure. Variation makes the structure visible.**

A grid is useful here because it makes repetition easy to see and reason about. The grid itself is not the subject.

The larger question is:

> **What can change while the system remains recognisably the same system?**

This question will return throughout the semester with parameter spaces, animation, agents, image processing and generative AI.

## From repetition to variation

Begin with something extremely simple:

> Draw one circle.

Then:

> Draw a circle every 40 pixels.

Then:

> Make every fifth circle larger.

Already there are three different ideas:

- a visual unit
- a repetition rule
- a variation rule

The important shift is from thinking about individual objects toward thinking about relationships.  
Instead of deciding where every circle should go, define a rule that determines where circles can appear.  
Instead of deciding the size of every circle individually, define how size changes.  
This is the beginning of generative thinking.

## Vera Molnár: order and interruption

Molnár is particularly useful in this session because her work shows that order and disorder do not need to be opposites.  
In the _Interruptions_ works, a clear underlying structure remains present even when parts are rotated, removed, displaced or interrupted.  
Use the work to discuss:

- repetition
- density
- absence
- disturbance
- controlled randomness
- the relationship between local changes and global structure

Ask:

> **How much disorder can be introduced before the original system disappears?**

Another useful question is:

> **What remains constant across different outputs?**

Do not frame Molnár simply as an example of randomness.  
The more useful idea is that variation operates **inside a designed system**.  
A random decision can still be constrained.

## Truchet tiles: local states, global patterns

Truchet tiles provide a very clear model of generative structure.  
The basic vocabulary can be tiny:

**one tile + two orientations**

Yet when repeated across a field, these local decisions can produce many different larger structures.  
This distinction between **local rule** and **global outcome** is important.

Ask:

- What information does one tile contain?
- How many possible states does it have?
- Does a tile need to know the final composition?
- Does it need to know what its neighbours are doing?
- How much complexity comes from the tile itself?
- How much comes from repetition?

A useful formulation is:

> **same unit + limited states + repetition = many possible compositions**

Truchet tiles are also a good bridge between manual rule systems and code.  
A tile can be drawn by hand, arranged physically, or generated computationally using exactly the same underlying idea.

## 10 PRINT: a tiny rule with large consequences

10 PRINT should come toward the end of the session, after repetition, grids, conditions and randomness have already been introduced.

The original program is:

```text
10 PRINT CHR$(205.5+RND(1)); : GOTO 10
```

Conceptually, it can be described without code:

> Choose one of two diagonal marks.
> Move to the next position.
> Repeat.

This is useful because almost everything introduced during the session becomes visible at once:

- repetition
- spatial structure
- two states
- random selection
- accumulation
- emergent global form

The program is extremely small, but its output can be visually rich.

Ask:

> **Where is the complexity?**

It is not located in any individual mark.  
The complexity emerges from repetition and the relationships created between many small decisions.  
The _10 PRINT_ book is useful to have physically available. Let it function as something to browse rather than something that needs to be explained page by page.  
It also demonstrates that a single line of code can be examined visually, technically, historically and culturally.

## Generative Design: reading systems through code

_Generative Design / Generative Gestaltung_ is useful here as a practical bridge from visual examples to readable code.  
The grid examples make relationships between visual structure and program structure relatively easy to identify.  
Rather than concentrating only on the resulting images, read the code as a description of a system.

Look for:

- the repeated unit
- the loop
- the calculation of `x` and `y`
- fixed values
- changing values
- relationships between variables
- conditions
- input
- randomness

A useful approach is to preserve most of an example while changing one relationship.

For example:

> Keep the grid, change the visual module.

Or:

> Keep the module, change how its size depends on position.

Or:

> Keep the structure, change the probability of one state.

The aim is not to reproduce the image exactly.  
The aim is to understand which parts of the code are responsible for which parts of the system.  
This introduces an important course-wide practice:

**read → identify → modify → observe**

## The examples as a progression

A useful order is:

1. **Vera Molnár - disturb a structure**
2. **Truchet tiles - repeat a unit with limited states**
3. **10 PRINT - repeat a probabilistic local decision**
4. **Generative Design - inspect and modify the implementation**

These examples move from artistic strategy toward increasingly explicit computational structure.  
Do not spend equal time on all four.  
A possible rhythm is:

- Molnár: 5 min
- Truchet tiles: 5 min
- 10 PRINT: 8 min
- Generative Design: 5 min

The goal is not to survey pattern-making.

The goal is to ask:

> **How can a small number of rules produce many outcomes?**

## From one mark to a field

Before using code, repeat a simple mark manually.

For example:

> Draw one vertical line.

Then:

> Move to the right and repeat.

Then:

> Rotate each line slightly more than the previous one.

Or:

> Every fifth line follows another rule.

This makes the transition to a loop easier to understand.

The same logic becomes:

**draw → move → draw → move → draw → move**

and eventually:

```js
for (let x = 20; x < width; x += 40) {
  line(x, 20, x, 100);
}
```

The syntax is compact, but the idea is still a repeated action.

## Variation is not randomness

This distinction is one of the most important ideas in the session.  
Variation can come from many sources.

### Systematic variation

A value changes according to another value.

For example:

**position → size**

or:

**column → rotation**

### Alternation

Two or more states repeat according to a sequence.

**A B A B A B**

### Conditional variation

Something changes when a condition becomes true.

> Every fifth element is larger.

### Probabilistic variation

A possible state is selected according to probability.

> 70% state A, 30% state B.

Randomness is therefore one possible source of variation, not a synonym for generative design.

A useful question is:

> **Where does the variation come from?**

If that question cannot be answered, simplify the system until it can.

## Breaking the pattern

Once a regular structure exists, introduce an exception.

For example:

- remove one element
- change one row
- enlarge one cell
- change every fifth element
- create an empty region
- introduce a different rule after a certain position

Ask:

> **How little can change while still changing the whole composition?**

An exception often makes the original pattern easier to perceive.  
This is one reason Molnár's work is so useful here. The interruption reveals the system that is being interrupted.  
The exception should not simply become another decorative effect.  
It should have a relationship to the underlying rule.

## Useful vocabulary

Useful terms for this session:

- unit
- repetition
- iteration
- sequence
- grid
- row
- column
- state
- variation
- alternation
- condition
- probability
- exception
- local rule
- global outcome

These are ways of describing what a system is doing rather than requirements for every exercise.

## Common difficulties

### The system becomes complicated immediately

Return to one visual unit.

Remove rules until the relationship can be explained clearly.

Ask:

> What is the smallest rule that still produces something interesting?

### Randomness is added everywhere

Ask:

> Can this variation come from position, sequence or a condition instead?

Compare a random change with a systematic one.  
Randomness becomes more meaningful when some parts of the system remain stable.

### Nested loops become abstract

Draw the movement spatially:

```text
→ → → → →
↓
→ → → → →
↓
→ → → → →
```

The inner loop moves across a row.  
The outer loop moves to the next row.  
Treat the computer as moving through the field one position at a time.

### The image is copied instead of the system

Ask:

> What is the rule behind the image?

Then change the visual vocabulary while keeping the rule.  
A Truchet-like system does not need to contain arcs.  
A 10 PRINT-like system does not need to contain diagonal lines.  
The transferable idea is the relationship between repeated local states.

### Too many variables change at once

Return to:

> **Change one thing. Observe what happens.**

Saving intermediate versions is useful.  
The creative process becomes easier to understand when cause and effect remain visible.

## Repetition in code

Introduce loops as a way of expressing repeated instructions, not as an isolated JavaScript concept.

Start with repeated commands:

```js
circle(20, 100, 20);
circle(60, 100, 20);
circle(100, 100, 20);
circle(140, 100, 20);
```

Ask:

> What changes?

Then replace the repeated commands with a loop.  
A useful way to read a loop is through four questions:

1. Where does it start?
2. When does it stop?
3. What changes each time?
4. What gets repeated?

Move from one loop to nested loops only after the first relationship is clear.
With nested loops, focus on spatial logic rather than terminology.

The important idea is:

> **The loop repeats the rule. The loop is not the visual idea itself.**

## Connection to later sessions

Session 2 introduces variation primarily across **space**.  
Session 3 will introduce variation across **time**.  
A value that changes from one cell to the next can later change from one frame to the next.

The same ideas will return in different forms:

**Session 3 - Change Over Time**  
Values change while a program is running.

**Session 4 - Behaviour & Agency**  
Many local decisions create larger behaviours and emergent structures.

**Session 5 - Parameter Spaces**  
Variation becomes an explicit space of possible outcomes.

**Session 6 - Images as Data**  
A grid becomes a field of pixels or samples.

The same basic question remains:

> **What stays fixed, and what is allowed to vary?**

## Connection to later AI work

This session will also become useful when generative AI is introduced.  
In p5.js, variation may be explicitly designed:

> choose state A or state B according to this probability.

In an AI image system, variation is produced by a much larger probabilistic model whose internal relationships are not directly authored or inspected in the same way.

Later, compare:

**explicit rules → controlled variation**

with:

**model conditioning → probabilistic variation**

Questions to revisit:

- Where does variation come from?
- Which parameters can be controlled?
- Which decisions remain hidden?
- Can an output be reproduced?
- What stays constant across several generations?
- When does unpredictability become useful?
- When does it make the system harder to understand?

The experience of building small explicit generative systems provides an important reference point for working critically with much larger generative models later.

## Sources worth keeping open during class

- Vera Molnár - Digital Art Museum
- Vera Molnár - _Interruptions_
- Truchet tiling references
- _10 PRINT CHR$(205.5+RND(1)); : GOTO 10_
- _Generative Design / Generative Gestaltung_
- Generative Design p5.js code package
- p5.js reference

The detailed links are collected on `examples.md`.
