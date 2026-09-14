# Session 1: Instructions & Systems

> Generative coding begins with rules.

Before we write code, we will explore what an instruction is, what makes a rule usable, and what happens when somebody else has to execute it.  
A rule can be precise, ambiguous, social, playful, poetic, or even impossible.  
Today we move through three kinds of execution:

**Human → Human**  
**Human → System**  
**Human → Computer**

- [🔴 HUMAN](#-human)
- [What we will explore](#what-we-will-explore)
- [1. What can an instruction be?](#1-what-can-an-instruction-be)
  - [Specify](#specify)
  - [Constrain](#constrain)
  - [Produce an event](#produce-an-event)
  - [Activate imagination](#activate-imagination)
- [2. Experience a rule system](#2-experience-a-rule-system)
- [3. From one rule to a system](#3-from-one-rule-to-a-system)
- [4. Exercise: Human to Human](#4-exercise-human-to-human)
  - [Author](#author)
  - [Executor](#executor)
  - [Compare](#compare)
  - [Revise](#revise)
- [5. Build a small rule system](#5-build-a-small-rule-system)
- [6. Human to Computer](#6-human-to-computer)
- [Session flow](#session-flow)
- [What to keep for your journal](#what-to-keep-for-your-journal)
- [Next session](#next-session)


## 🔴 HUMAN

For this session, work without generative AI.

Do not use AI to:

- invent your rules
- write your p5.js code
- debug the exercise
- write your process notes

You can use the p5.js reference, course examples, your classmates and the instructor.  
The point is to experience the process yourself before we introduce AI later in the semester.

## What we will explore

By the end of the session, you should have experienced how to:

- recognise a creative work as a system of rules
- distinguish between an instruction and its outcome
- identify what a rule specifies and what it leaves open
- notice ambiguity and hidden assumptions
- build a simple rule system from a few small actions
- revise a rule after seeing somebody execute it
- translate a simple human instruction into p5.js

## 1. What can an instruction be?

We start by looking at different ways artists and designers have used instructions.

### Specify

**Sol LeWitt**

An instruction can describe what should happen with considerable precision.  
But even precise instructions leave questions:

- Who executes them?
- What still needs to be interpreted?
- Will two executions be identical?
- Where does the artwork exist: in the rule or in the result?

### Constrain

**Conditional Design**

The book *Conditional Design* is an additional course reference for this session. A PDF copy will be linked here after it has been added to the repository.

Instead of defining the final image, rules can define what participants are allowed to do.  
The result emerges while people act inside those constraints.

Questions:

- What is controlled?
- What is left open?
- How does one person's decision affect the next person's possibilities?

### Produce an event

**George Brecht and Alison Knowles**

An instruction does not need to produce a drawing.  
It can produce an action, event, performance or situation.

### Activate imagination

**Yoko Ono**

An instruction can also be poetic, impossible or completed partly in your imagination.  
This raises another question:

> Does an instruction need to be physically executable to create something?

The main question for today is:

> **How much should a rule determine, and how much should it leave open?**

→ [Explore more instruction-based works and examples](./examples.md)

## 2. Experience a rule system

Before inventing your own system, participate in one.  
We will use a rule-based drawing exercise inspired by the Conditional Design archive. Your task is not to make the best drawing.  
Pay attention to:

- what the rules determine
- what you determine
- what other participants determine
- what becomes impossible after someone makes a choice
- what happens that nobody planned

Afterwards, compare the different outcomes.

_Would the same rules produce exactly the same result if we started again?_

## 3. From one rule to a system

It is easy to make a rule too complicated. Start smaller. For example:

**Place a point.**

Then add one thing:

**Place two points.**

Then define a relationship:

**Connect the two points with a line.**

Then introduce variation:

**Place two points anywhere on the page and connect them.**

Then introduce repetition:

**Repeat the process.**

Then introduce a constraint:

**A new line may not cross an existing line.**

Then define an ending:

**Stop when no new line can be added.**

A system can grow from a very small number of ideas.  
When you get stuck, try building your system using these ingredients:

- starting condition
- action
- relationship
- repetition
- variation
- constraint
- condition
- stopping rule

You do not need all of them.  
Start with the smallest system that produces something interesting.

## 4. Exercise: Human to Human

Work in pairs.

### Author

Create a small drawing using simple elements such as:

- points
- lines
- circles
- rectangles
- filled areas

Do not show the drawing to your partner.  
Write instructions that should allow another person to reproduce it.  
Keep the system small.  
Aim for approximately 6 to 10 instructions.

### Executor

Follow the instructions without seeing the intended drawing.  
During the first execution:

- do not ask questions
- do not receive help from the author
- mark places where you are unsure what an instruction means
- make a decision and continue

### Compare

Reveal the intended drawing.  
Put these three things beside each other:

1. the original idea
2. the written instructions
3. the executed result

Discuss:

- What was interpreted differently?
- What information was missing?
- What did the author assume?
- Which instructions were actually clear?
- Did any unexpected interpretation make the result more interesting?

### Revise

Change only the rules that need changing.  
Then test the instructions again.  
Do not try to remove every possible variation.  
Decide which ambiguity is a problem and which ambiguity might be useful.

## 5. Build a small rule system

Now create a simple system without starting from a finished image.  
Use a limited vocabulary:

- point
- line
- circle
- rectangle

Begin with one action.  
Then add relationships, variation or constraints one at a time.  
Try to include:

- a clear starting condition
- at least one relationship
- at least one rule that can produce variation
- a stopping condition

Test your system yourself or give it to another student.  
If it becomes difficult to explain, simplify it.

## 6. Human to Computer

Now we change executor.  
Instead of giving instructions to another person, we give them to a computer.  
A computer does not interpret an instruction in the same way a person does. 
 
Consider:

> Draw a circle near the centre of the page.

A person can make many decisions automatically. A computer needs more information.

For example:

```js
function setup() {
  createCanvas(400, 400);
  background(240);

  circle(200, 200, 80);
}
```

Suddenly we had to decide:

- the size of the canvas
- the position of the circle
- the size of the circle
- what "centre" means

For today's coding exercise, keep the vocabulary small:

```js
createCanvas();
background();
point();
line();
circle();
rect();
fill();
stroke();
```

Translate part of one of your rule systems into p5.js.  
Do not use loops, randomness or animation yet.  
Those come next.  
The goal is not to make a finished artwork.  
The goal is to discover:

> **What did the human understand that the computer needs you to specify?**

## Session flow

Approximately:

- 20 min: introduction and instruction examples
- 20 min: collective rule system
- 35 min: Human to Human exercise
- 10 min: break
- 20 min: build a small rule system
- 35 min: Human to Computer
- 10 min: discussion and journal capture

## What to keep for your journal

Keep evidence of the process, not only the successful result.

Save:

- your first instruction set
- the first execution
- moments of confusion or ambiguity
- the revised instructions
- the second execution
- your small rule system
- a sketch or diagram of the system
- your p5.js translation

Add a few short observations.

For example:

- One thing my executor interpreted differently was...
- One rule I changed was...
- One ambiguity I decided to keep was...
- One thing I had to make explicit for the computer was...

You do not need to write a long reflection.

## Next session

In Session 2 we take simple rules and introduce:

- repetition
- loops
- variation
- randomness
- exceptions

A single rule can produce one result.  
Repeating and varying rules begins to produce a generative system.

→ [Instruction examples and references](./examples.md)

→ [Deeper notes on this session](./teacher-notes-h.md)
