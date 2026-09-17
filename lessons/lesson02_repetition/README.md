# Session 2: Repetition & Variation

> Repetition creates structure. Variation makes the structure visible.  

In Session 1 we created rules, tested them with people, revised them and translated some of them into code. Today we take those rules and repeat them.

The main progression is:  

**make a unit → repeat it → vary it → interrupt it → compare outcomes**


## 🔴 HUMAN

Work without generative AI for this session.  
Do not use AI to write the exercises, debug the code or generate your journal reflection.  
Use the p5.js reference, examples, classmates and the instructor when you need help.  
The goal is to experience repetition, loops, variation and debugging directly before AI enters the workflow later.

## What we will explore

By the end of the session, you should be able to:

- use a `for` loop to repeat an action
- use variables to control position, size and spacing
- create rows and grids using nested loops
- distinguish systematic variation from randomness
- introduce exceptions and conditions into a repeated structure
- understand how simple local rules can create complex global patterns
- develop several outcomes from the same underlying system

→ [Examples and references](./examples.md)

## 1. Repeat a simple rule

Begin on paper.
Choose one very simple mark:

- a point
- a line
- a circle
- an arc
- a rectangle

Repeat it approximately 20 times using one rule.
For example:

> Draw a circle every 2 cm.

Then change one thing:

> Every fifth circle is twice as large.

Or:

> Rotate each line slightly more than the previous line.

Ask:

- What remains constant?
- What changes?
- When does repetition become a pattern?
- How much variation is needed before the system feels different?

Do not begin with a complicated composition. Start with one clear relationship.

## 2. Repetition in code

Writing the same command repeatedly works, but quickly becomes inefficient:

```js
circle(20, 100, 20);
circle(60, 100, 20);
circle(100, 100, 20);
circle(140, 100, 20);
```

A loop describes the repetition as a rule:

```js
for (let x = 20; x < width; x += 40) {
  circle(x, 100, 20);
}
```

The important parts are:

- where the repetition starts
- the condition for continuing
- what changes after each repetition
- what happens inside the loop

The loop is not the visual idea.
It is the mechanism that repeats the visual rule.

## 3. From a row to a grid

One loop can create a row. Two loops can create a grid:

```js
for (let y = 20; y < height; y += 40) {
  for (let x = 20; x < width; x += 40) {
    circle(x, y, 20);
  }
}
```

The outer loop moves through the rows.
The inner loop moves across each row.

Experiment with:

- spacing
- number of rows and columns
- size of the element
- different shapes
- relationships between `x`, `y`, size and position

A grid is useful because it makes the structure of repetition visible.
The grid itself is not the goal.

## 4. Build a repeated system

Sketch one simple visual unit on paper first.
Use a limited vocabulary:

- line
- circle
- arc
- rectangle

Then repeat it across a row or grid in p5.js.
Start with a version where every unit is identical.

Save this version before introducing variation.

This is your baseline.

## 5. Introduce variation

Variation does not automatically mean randomness.
Start by changing values systematically.

### Position

Make the position depend on the row or column.

### Size

Increase or decrease the size across the composition.

```js
let size = 10 + x * 0.05;
circle(x, y, size);
```

### Orientation

Rotate elements according to their position.

### Alternation

Change every second element.

```js
if (column % 2 === 0) {
  // one state
} else {
  // another state
}
```

### Gradual change

Let one value slowly move from one state to another across the grid.

Create several versions.
Change one variable at a time so that you can understand what caused the result.

## 6. Break the pattern

Once you have created a regular structure, introduce an exception.

For example:

- one cell follows another rule
- every fifth element changes
- one row is different
- one area remains empty
- one element is much larger
- elements change after a certain position

Ask:

> **How little can you change while still changing the whole composition?**

An exception can make the underlying rule easier to see.

## 7. Controlled randomness

Now introduce randomness carefully.

For example:

```js
let size = random(10, 30);
circle(x, y, size);
```

Compare this with your earlier systematic variations.

Ask:

- What control did you lose?
- What possibilities did you gain?
- Is every random result equally interesting?
- Which parameters should remain fixed?
- Which parameters can vary?

Randomness is only one way to create variation.

## 8. 10 PRINT

One of the simplest examples of repetition and variation comes from a one-line Commodore 64 BASIC program:

```text
10 PRINT CHR$(205.5+RND(1)); : GOTO 10
```

At each position, the program chooses between two diagonal characters and then repeats the process. A very small local decision produces a much larger visual structure.

Recreate the idea in p5.js using two possible diagonal lines.

For example:

```js
if (random() < 0.5) {
  line(x, y, x + cellSize, y + cellSize);
} else {
  line(x + cellSize, y, x, y + cellSize);
}
```

Then make **one meaningful variation**.

You could change:

- probability
- cell size
- possible marks
- number of states
- colour
- direction
- spacing

Try to understand the effect of each change before adding another one.

→ [10 PRINT book and further examples](https://10print.org/)

## Start simple, then complexify

A useful workflow for today is:

**one unit → repeat → observe → change one value → observe again**

Avoid adding many techniques at the same time.
If the system stops making sense, simplify it.

Useful questions:

- What is the smallest rule in my system?
- What stays constant?
- What is allowed to vary?
- Where does variation come from?
- What happens if I change only one parameter?
- Does randomness improve the system or only make it less predictable?

## What to keep for your journal

Document the evolution of the system, not only the final image. Keep:

- your first paper sketch
- the basic repeated version
- at least two systematic variations
- one version containing an exception
- one controlled-random version
- your 10 PRINT variation
- several outputs produced by the same rules

Add a few short observations:

- What remained constant across the variations?
- Which small change had the largest effect?
- What happened when you introduced randomness?
- Did a mistake or unexpected result lead somewhere interesting?
- Which version would you continue developing, and why?

You do not need to write a long reflection.

## Next session

In Session 3 we introduce **change over time**.
Instead of asking only how a system varies across space, we will ask how its values, states and behaviour can change while the program is running.

→ [Examples and references](./examples.md)  
→ [Teacher notes](./teacher-notes.md)
