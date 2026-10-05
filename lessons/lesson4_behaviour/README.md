# Session 4: Behaviour & Agency

> A system can change over time. A behaviour emerges when that change begins to respond to rules, conditions and its environment.  
> In Session 3 we controlled how values changed from one moment to the next. Today we give elements their own state and rules and allow them to respond.

The main progression is:  
**state → movement → response → feedback → multiple agents → emergent behaviour**

## 🟠 EXPLAIN → 🟡 COLLABORATE

Begin the session in **🟠 EXPLAIN** mode.

Use AI to:

- explain concepts
- interpret errors
- explain unfamiliar code
- help you understand why a behaviour is not working as expected

First build a meaningful version of the system yourself.

Once you can explain the basic behaviour, move into **🟡 COLLABORATE** mode.

You can then use AI to:

- debug
- critique the behaviour
- suggest alternative implementations
- refactor repeated code
- extend a system you already understand

Do not begin by asking AI to generate a complete agent system or drawing machine.

Before collaborating, you should be able to answer:

> **What rules currently control the behaviour?**

## What we will explore

By the end of the session, you should be able to:

- distinguish movement from behaviour
- use variables to describe the state of an element
- use velocity to control movement
- change behaviour when a condition becomes true
- make elements respond to boundaries and input
- understand feedback as a relationship between current and future states
- create several elements following the same local rules
- observe how simple behaviours can produce complex global outcomes
- build a system that leaves traces or produces drawings through its behaviour

→ [Examples and references](./examples.md)

## 1. From change to behaviour

In Session 3 we created change by updating values:

```js
x = x + 1;
```

The rule is simple and predictable.

The element always moves in the same direction.

A behaviour begins to appear when the next change depends on the current situation.

For example:

```js
if (x > width) {
  speed = -speed;
}
```

Now the movement responds to the environment.

The important shift is:

**change**

```text
value → new value
```

becomes:

**behaviour**

```text
current state + condition → response → new state
```

## 2. Give an element state

An element can have several values that describe its current state.

For example:

```js
let x = 100;
let y = 100;

let vx = 2;
let vy = 1;
```

`x` and `y` describe position.

`vx` and `vy` describe velocity.

Inside `draw()`:

```js
x = x + vx;
y = y + vy;

circle(x, y, 20);
```

The element now has a direction and speed.

Try changing:

- horizontal velocity
- vertical velocity
- starting position
- speed
- direction

Ask:

> **Which values describe what the element is, and which values describe what it does?**

## 3. Respond to boundaries

Without another rule, the element eventually leaves the canvas.

Introduce a condition:

```js
if (x > width || x < 0) {
  vx = -vx;
}

if (y > height || y < 0) {
  vy = -vy;
}
```

The element now responds to its environment.

A small rule creates a recognisable behaviour:

> move → encounter boundary → change direction → continue

Change the response.

Instead of bouncing, an element could:

- stop
- wrap to the opposite side
- change speed
- change size
- change colour
- leave a mark
- choose a new direction

The boundary is the same.

The behaviour comes from the response.

## 4. Respond to something else

An element can respond to more than the edge of the canvas.

For example, calculate its distance from the mouse:

```js
let d = dist(x, y, mouseX, mouseY);
```

Then use that distance as part of a rule.

For example:

```js
if (d < 100) {
  // change behaviour
}
```

The mouse could become:

- something to follow
- something to avoid
- a source of attraction
- a source of disturbance
- a switch between behaviours

Do not think only in terms of interaction.

The important idea is:

> **Behaviour depends on relationships.**

## 5. Feedback

A system has feedback when what happens now affects what can happen next.

Consider:

```text
position → boundary → direction changes → new position → boundary...
```

The output of one moment becomes part of the input for the next.

This creates a feedback loop.

Feedback can be simple:

> hit edge → reverse direction

or more complex:

> move → leave trace → detect trace → change movement

Ask:

- What information does the system remember?
- What changes because of previous actions?
- Can the system affect its own future behaviour?

Feedback is one of the important differences between a fixed animation and a behaving system.

## 6. Introduce variation

Perfectly predictable behaviour can become repetitive.

Introduce a small amount of variation.

For example:

```js
vx = vx + random(-0.1, 0.1);
vy = vy + random(-0.1, 0.1);
```

Or only introduce variation under certain conditions:

```js
if (x > width) {
  vx = random(-3, -1);
}
```

Compare:

**random movement**

with:

**a rule that occasionally uses randomness**

These are not the same thing.

Try to keep the underlying behaviour visible.

Ask:

> **Does randomness create behaviour, or does it only disturb it?**

## 7. From one element to many

A single element can already behave.

Several elements following the same rules can produce something much less predictable.

Imagine five elements that all:

- move
- respond to boundaries
- change direction
- leave traces

Even if the rule is identical, different starting states can produce different trajectories.

This introduces an important distinction:

**local behaviour**  
what one element does

**global behaviour**  
what becomes visible when many elements act together

The individual element does not need to know what the final composition should look like.

## 8. Agents

For this session, an **agent** is simply an element that has:

- a state
- rules
- the ability to update its state
- some way of responding to its environment

It does not imply intelligence or consciousness.

A very simple agent might only know:

```text
where am I?
which direction am I moving?
what happens if I reach an edge?
```

A more complex one might respond to:

- another agent
- the mouse
- a trail
- distance
- density
- sound
- time
- probability

Complex behaviour does not necessarily require complex agents.

## 9. Drawing machines

A drawing machine is a useful way to explore behaviour because movement becomes visible through the marks it produces.

Instead of drawing every line directly, design a system that decides **how marks are made**.

Your program might behave like:

- a pendulum
- a wandering pen
- a reluctant brush
- a machine attracted to the mouse
- several drawing agents
- a mechanism that becomes less accurate over time
- a system that reacts to its previous marks
- a drawing tool that deliberately misunderstands input

The important shift is:

**drawing an image**

becomes:

**designing something that draws**

### Build a drawing machine

Create a system with:

1. a movement rule
2. at least one response or condition
3. a mark-making rule
4. one source of variation
5. a recognisable character

Examples of character:

- precise
- nervous
- slow
- stubborn
- chaotic
- hesitant
- repetitive
- collaborative
- forgetful

Use the same machine to produce several different drawings.

→ [Drawing machine references](./drawing-machines.md)

## 10. Develop the behaviour gradually

A useful process is:

**move → respond → vary → multiply → observe**

Do not begin with many agents and many rules.

Start with one element.

Ask:

> What does it do?

Then add one relationship:

> What does it respond to?

Then add one consequence:

> How does that response change what happens next?

Only then introduce additional agents or variation.

Useful questions:

- What is the smallest behaviour in the system?
- What information does the element know?
- What can it respond to?
- What changes its future state?
- What is deterministic?
- What is probabilistic?
- Does the system remember anything?
- What happens when several elements follow the same rule?
- Is the global result directly designed or does it emerge?

## What to keep for your journal

Document the development of the behaviour, not only the final drawing.

Keep:

- your first behaviour diagram or sketch
- the simplest moving version
- one boundary or response experiment
- one feedback experiment
- one version using controlled variation
- one experiment with several elements
- at least three outputs from your drawing machine
- one unexpected behaviour that changed your idea

For the system, try drawing a simple diagram such as:

```text
move
  ↓
sense
  ↓
respond
  ↓
update state
  ↓
move again
```

If you move into **🟡 COLLABORATE** mode, add a short note:

- What existed before AI was used?
- What did you ask AI to help with?
- What changed afterwards?
- Which important decisions remained yours?

You do not need to include complete prompt histories.

## Next session

In Session 5 we move from individual behaviours toward **parameter spaces**.

Instead of changing one system through trial and error, we will identify its important variables and explore families of possible outcomes systematically.

→ [Examples and references](./examples.md)  
→ [Drawing machine references](./drawing-machines.md)  
→ [Notes on this session](./teacher-notes.md)