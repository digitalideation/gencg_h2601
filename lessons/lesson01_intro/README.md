# Session 1 — Instructions & Systems

> **Generative coding means designing rules and systems that produce outcomes.**

This session begins with instructions executed by people, then uses the same questions to make a small transition into code. Its working sequence is:

## **experience → formulate → execute → compare → revise → encode**

## 🔴 HUMAN

This session is an independent baseline:

- **Do not use generative AI to write the instructions.**
- **Do not use generative AI to write or debug the p5.js code.**
- **Do not use generative AI to produce the process reflection.**
- You may use peers, the instructor, supplied examples, and the [p5.js reference](https://p5js.org/reference/).

Trying the process independently establishes a baseline for later comparisons with AI. Asking people for help is encouraged: describe what you expected, show what happened, and identify what you have already tried. Help peers in the same way, without taking over their work.

## Learning objectives

By the end of the session, students should be able to:

- Recognise a generative work as a **system of rules**, rather than a visual style.
- Write a finite sequence of executable instructions.
- Identify ambiguity, hidden assumptions, and interpretation in an instruction set.
- Revise rules after observing an unexpected result.
- Translate a small human-readable procedure into ordered p5.js commands.
- Explain the difference between **Human → Human** and **Human → Computer** execution.

## Before class

Preparation is deliberately minimal:

- Confirm access to the [p5.js web editor](https://editor.p5js.org/) or the supported local environment.
- Bring paper and a drawing tool.
- Bring one example of instructions encountered in ordinary life.

No journal-branch setup is required. The journal will move to a separate repository; until it exists, keep the process evidence listed below.

## Schedule (150 minutes)

| Time | Activity |
| --- | --- |
| 00:00–00:15 | Course framing: what is a generative system? |
| 00:15–00:30 | Four examples: authored, open, collective, everyday |
| 00:30–00:40 | Demonstrate the Human → Human exercise |
| 00:40–01:05 | Paired procedural drawing, first execution |
| 01:05–01:20 | Compare results and annotate ambiguity |
| 01:20–01:30 | Break |
| 01:30–01:50 | Revise instructions and execute again |
| 01:50–02:00 | Discuss Human → Human versus Human → Computer |
| 02:00–02:20 | Translate selected instructions into p5.js |
| 02:20–02:25 | Share contrasting translations |
| 02:25–02:30 | Exit ticket |

## Part 1: Course framing

The central proposition for the course is:

> **Generative coding means designing rules and systems that produce outcomes.**

Briefly distinguish:

- an outcome from the system that produced it;
- directly drawing an image from designing instructions for an image;
- executing a rule from interpreting a rule;
- deterministic instructions from instructions that contain choice or chance.

Use the [_Introduction_ slides][intro-slides] to frame the course and the [_History_ slides][history-slides] only for a short through-line from instruction-based art to computational systems. The aim is not a full historical survey.

## Part 2: Four relationships between rules and outcomes

These are four short comparisons, not four separate exercises. Spend no more than five minutes on any one reference. In each case, distinguish the rule author, executor, interpretation, and outcome.

### 1. Precise-looking artistic instructions — Sol LeWitt

First show only the instruction for [Sol LeWitt's *Wall Drawing 118*][wall-drawing-118]:

> Fifty randomly placed points, all connected by straight lines.

Before revealing or discussing the execution, ask students to mark the words that seem exact and the words that leave work for another person. Then reveal the existing image:

![Sol LeWitt, Wall Drawing 118](images/wd118.jpg)

Keep the focus on the relationship among LeWitt as author of the system, the written instruction, the installers or drafters who execute it, and the resulting wall drawing—not on a long biography.

- Which words appear precise?
- Which words still require interpretation?
- Who makes the compositional decisions?
- Is each execution an original work, an instance of the work, or both?
- Where does authorship reside?

### 2. Deliberately open instructions — an event score

In Yoko Ono's *Cloud Piece* (1963), later published in *Grapefruit*, the participant is invited to imagine clouds dripping and to make a hole in the garden to receive them. This is a brief paraphrase rather than a script to reproduce. See the [Museum of Modern Art's account of *Grapefruit*][moma-grapefruit].

Unlike LeWitt's apparently precise instruction, this score can produce an imaginary, impossible, poetic, or subjective action. Ambiguity is artistic material; a successful execution need not be a visually accurate illustration.

- Is this instruction intended to be followed literally?
- What does the executor contribute?
- Can an ambiguous algorithm still be a meaningful system?
- What would be lost if the instruction became completely precise?

### 3. Collective rule systems — Conditional Drawing

Use one activity adapted from the [Conditional Design archive][conditional-archive] as the primary social-system example. Groups of three or four need one large sheet of paper and a differently coloured pen for each participant.

1. Each participant places one point anywhere on the sheet.
2. Take turns. On a turn, extend one existing point or line-end with a single straight line in your own colour.
3. The new line must end at another point or line, and must not cross an existing line.
4. Continue clockwise; do not erase or move earlier marks.
5. Stop after twelve minutes or when the group agrees that no legal move remains.

This compact classroom protocol is not a claim to reproduce one archived score exactly. It uses Conditional Design's collective method to make feedback visible: every local choice changes what later participants can do, and the rules' authors did not draw the outcome in advance.

![A Conditional Design collective drawing](images/poster.jpg)

- Which decisions belong to the rules?
- Which belong to the participants?
- Does the order of participation matter?
- Can the final result be predicted from the initial rules?
- What happens when participants interpret a rule differently?

### 4. Everyday instructions — a non-art comparison

In small groups, choose one familiar procedure: a recipe, assembly diagram, knitting or weaving pattern, board-game rule, choreography notation, transit procedure, paper-folding directions, or classroom routine. Do not default to the comic “make a sandwich” test; investigate embodied skill and assumptions seriously if food preparation is selected.

Annotate the procedure to identify:

- required inputs;
- sequence and repetition;
- conditions;
- assumed knowledge;
- stopping condition;
- tolerance for variation.

These procedures demonstrate that algorithms predate computers and operate far beyond them. Compare what the procedure states with what a competent practitioner supplies.

### Comparison table

Treat these entries as prompts, not definitive judgements. Students may disagree and revise the table after discussion.

| Example | Rule author | Executor | Rule precision | Source of variation | Predictability |
| --- | --- | --- | --- | --- | --- |
| Sol LeWitt | Artist | Installers/drafters | Apparently precise but interpreted | Placement and execution | Partial |
| Event score | Artist | Reader/participant | Intentionally open | Imagination and interpretation | Low |
| Conditional Design | Designers/group | Multiple participants | Constrained social protocol | Interaction and sequence | Partial |
| Everyday procedure | Community/designer/user | Practitioner | Depends on assumed knowledge | Materials, context, skill | Variable |
| p5.js procedure | Student | Computer | Syntactically strict | Values and programmed rules | High unless variation is encoded |

### Counterexample: appearance is not evidence

Show this image without initially revealing its process or filename:

![Repeated circular forms in black and white](../../assets/images/circles01-bw.png)

- Can visual appearance prove that a work is generative?
- Could this image have been drawn manually?
- What evidence would reveal the system?
- Are repeated forms enough to establish an algorithm?

Only after discussion, reveal any available process evidence. The course studies processes and systems, not merely a recognisable “generative” aesthetic.

## Part 3: Core Human → Human exercise

Work in pairs with separate roles:

- **Author:** writes the instructions and has an intended result in mind.
- **Executor:** follows the instructions without seeing the intended result.

Use a constrained material and vocabulary set so the focus remains on rule formulation rather than illustration:

- one sheet of paper;
- one black pen;
- points, lines, circles, rectangles, and filled areas;
- six to ten instructions;
- ten minutes for execution.

The author's instruction set must define:

1. the starting condition;
2. the order of operations;
3. relevant positions or relationships;
4. any repetition;
5. the stopping condition.

### First execution

- The executor may not ask clarifying questions.
- The author may not intervene.
- The executor marks or records moments of uncertainty without resolving them aloud.
- After execution, both students annotate those moments.

This is the first pass through **experience → formulate → execute → compare**. Treat an unexpected result as evidence about the system, not simply as failure by the executor.

## Part 4: Compare and diagnose

Place the intended idea, written instructions, and resulting drawing together. Identify at least **three consequential phrases or omissions**, then classify each using these categories:

| Category | Diagnostic |
| --- | --- |
| **Ambiguity** | The wording supports multiple interpretations. |
| **Assumption** | Necessary information was never stated. |
| **Sequence** | The order changes or prevents the result. |
| **Intentional openness** | Variation is deliberately left to the executor. |

Discuss what the executor inferred, where the result diverged, and which differences matter. Documentation of unexpected results is evidence that makes the rules available for revision.

## Part 5: Revision

Rewrite **only** the instructions that caused meaningful differences. If class size permits, give the revised version to a new executor and repeat the drawing without clarification or intervention.

Compare the two executions:

- What became more precise?
- What variation remained?
- Did greater precision improve the work?
- Was any ambiguity worth preserving?

Revision is part of algorithm design, not a correction performed after “the real work.” This completes **revise** in the session sequence and prepares the rules to be encoded.

## Part 6: Human → Computer bridge

Introduce p5.js as another executor—one that requires a different form of precision. Translate a **small subset** of the revised instructions into ordered drawing commands.

### Coding scope

Use only what is needed from this small set:

- `setup()`;
- `createCanvas()`;
- canvas coordinates;
- `background()`;
- `stroke()` and `fill()`;
- primitives such as `point()`, `line()`, `circle()`, and `rect()`.

End the Human → Human exercise with one deliberately tiny translation. Keep the three representations together.

**Natural-language instruction:** Draw a circle near the centre, then place a rectangle below it.

**Ordered p5.js statements:**

```js
function setup() {
  createCanvas(400, 400);
  background(240);
  stroke(0);
  fill(255);
  circle(200, 180, 80);
  rect(160, 240, 80, 50);
}
```

**Rendered result:**

![A white circle above a white rectangle on a light grey square](images/ordered-primitives.svg)

Do **not** require loops, arrays, randomness, animation, `map()`, object-oriented code, or a polished final composition. Loops, randomness, and animation belong in Sessions 2 and 3.

Use the translation to ask:

- What could the human infer that the computer could not?
- Which values had to become explicit for the computer?
- Does the code express the artistic intention, or only drawing operations?
- What would need to be added to produce repetition or variation?

This final **encode** stage is not about making the best image. It exposes the difference between **Human → Human** and **Human → Computer** execution.

## Process evidence to retain

Keep the following material for the future journal repository:

- the first instruction set;
- a photograph or scan of the first execution;
- annotations identifying at least three ambiguities or assumptions;
- the revised instruction set;
- a photograph or scan of the second execution;
- a screenshot or link to the small p5.js translation;
- three concise observations:
  1. one thing the executor interpreted unexpectedly;
  2. one rule you revised;
  3. one difference between a human and computer executor.

Do not write a long reflective essay. For now, retain these items rather than committing them to a journal branch.

## Exit ticket

Complete these three statements:

1. “The most important rule in my system was…”
2. “My executor had to assume…”
3. “Before a computer could execute this, I had to…”

The responses will identify concepts to revisit at the start of Session 2.

## Checkpoint for Session 2

Bring:

- one simple visual unit or mark;
- one plain-language placement rule;
- one sketch showing the unit repeated at least five times;
- one proposed exception to the repetition.

This is a direct bridge into **Session 2 — Repetition & Variation** without teaching loops in Session 1.

## Optional examples and practice

The following are extensions, not Session 1 core activities:

- explore selected [p5.js tutorials](https://p5js.org/tutorials/) or the [p5.js reference](https://p5js.org/reference/);
- “Draw then code” and “One with everything” exercises;
- build an imaginary map from simple primitives;
- play or analyse [Sprouts][sprouts], a compact game with explicit constraints, turns, legal moves, and an end condition;
- keep Moniker's [*The Beach*](https://conditionaldesign.org/workshops/the-beach/) as an optional pointer only. Its fuller treatment belongs in Session 4 when that lesson addresses **Behaviour & Agency**, where self-organisation and emergence are the central connections.

### Explore further

Use these only when they support a particular question; they are not additions to the four-example presentation:

- [Sprouts][sprouts] for legal moves and stopping conditions;
- [*The Beach*](https://conditionaldesign.org/workshops/the-beach/) for later discussion of self-organisation;
- other short scores in the [MoMA overview of *Grapefruit*][moma-grapefruit] for intentionally open execution.

Additional references should add a relationship not already represented, support a specific question or activity, take under five minutes to explain, and have a reliable accessible source. They should broaden practices, media, or perspectives without implying that generative practice began with computers or requiring a historical detour. Confirm that any reproduced material fits the course site's copyright and attribution practices.

Iteration, loops, randomness, and animation are deferred to Sessions 2 and 3.

## References

- [_Introduction_ slides][intro-slides]
- [_History_ slides][history-slides]
- [Sol LeWitt at MASS MoCA](https://massmoca.org/sol-lewitt/)
- [Conditional Design archive](https://conditionaldesign.org/archive)
- [Yoko Ono, *Grapefruit*, Museum of Modern Art][moma-grapefruit]
- [p5.js reference](https://p5js.org/reference/)
- [The Coding Train](https://thecodingtrain.com/)
- [The Nature of Code](https://natureofcode.com/)

[intro-slides]: https://digitalideation.github.io/gencg_h2501/slides/intro.html
[history-slides]: https://digitalideation.github.io/gencg_h2501/slides/history.html
[sprouts]: https://nrich.maths.org/2413
[wall-drawing-118]: https://jessicacarnegie.com/sol-lewitt-wall-drawing-118
[conditional-archive]: https://conditionaldesign.org/archive
[moma-grapefruit]: https://www.moma.org/learn/moma_learning/yoko-ono-grapefruit-1964/
