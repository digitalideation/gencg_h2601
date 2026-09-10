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
| 00:15–00:30 | Historical examples and rule analysis |
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

## Part 2: Looking outward

### Sol LeWitt

Consider [*Wall Drawing 118*][wall-drawing-118]:

> Fifty randomly placed points, all connected by straight lines.

![Sol LeWitt, Wall Drawing 118](images/wd118.jpg)

The sentence is concise, but it still establishes a system: someone must place points, decide what “randomly” permits, and connect them. The wall drawing is an execution of the instruction, not the instruction itself.

### Conditional Design

Look at selected prompts from the [Conditional Design archive](https://conditionaldesign.org/archive) or workbook. These projects foreground rules, collaboration, constraints, and the decisions made during execution.

![Conditional Design poster](images/poster.jpg)

For **each** reference, ask:

1. Where are the rules?
2. Who executes them?
3. Which decisions are specified?
4. Which decisions remain open?
5. Would two executions be identical?
6. Is interpretation a mistake, or part of the work?

### Optional short examples

If useful, briefly demonstrate [Sprouts][sprouts] or Moniker's [*The Beach*](https://conditionaldesign.org/workshops/the-beach/) as further systems of rules and social interpretation. Do not run them as separate 30-minute activities.

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

For example, “draw a circle near the centre, then place a rectangle below it” must become an explicit order with numeric positions and sizes:

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

Do **not** require loops, arrays, randomness, animation, `map()`, object-oriented code, or a polished final composition. Iteration and randomness belong in Session 2.

Use the translation to ask:

- What could the human infer that the computer could not?
- Which natural-language instruction had to be divided into smaller steps?
- Which decisions became numeric?
- Did the computer remove ambiguity, or merely relocate it into the code?
- What would need to change before the computer could perform repetition?

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

## Optional practice

The following are extensions, not Session 1 core activities:

- explore selected [p5.js tutorials](https://p5js.org/tutorials/) or the [p5.js reference](https://p5js.org/reference/);
- “Draw then code” and “One with everything” exercises;
- build an imaginary map from simple primitives;
- play or analyse [Sprouts][sprouts] and [*The Beach*](https://conditionaldesign.org/workshops/the-beach/).

Iteration, loops, and randomness are deferred to Session 2.

## References

- [_Introduction_ slides][intro-slides]
- [_History_ slides][history-slides]
- [Sol LeWitt at MASS MoCA](https://massmoca.org/sol-lewitt/)
- [Conditional Design archive](https://conditionaldesign.org/archive)
- [p5.js reference](https://p5js.org/reference/)
- [The Coding Train](https://thecodingtrain.com/)
- [The Nature of Code](https://natureofcode.com/)

[intro-slides]: https://digitalideation.github.io/gencg_h2501/slides/intro.html
[history-slides]: https://digitalideation.github.io/gencg_h2501/slides/history.html
[sprouts]: https://nrich.maths.org/2413
[wall-drawing-118]: https://jessicacarnegie.com/sol-lewitt-wall-drawing-118
