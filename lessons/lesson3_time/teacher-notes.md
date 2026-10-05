# Teacher Notes: Session 3 - Change Over Time

These notes are background for Session 3, with teaching prompts and a few possible directions. They can also be shared with anyone who wants to go a bit deeper.

## Why this session exists

The first two sessions are mostly spatial.

In Session 1, we define rules.  
In Session 2, we repeat those rules across a page or canvas.

Session 3 introduces another dimension:

> **What happens when the system changes while it is running?**

I think the main transition is quite simple:

**variation across space → variation across time**

A value that changed from one cell to the next in Session 2 can now change from one frame to the next.

The session should probably move through something like:

**static value → changing value → state → cycle → rhythm → time as input**

The clock comes later as one possible case study. I wouldn't make the whole session about clocks.

The more general question is:

> **How can time become part of a generative system?**

## From repetition in space to repetition in time

I would start by making the relationship with Session 2 very explicit.

A `for` loop repeats something across space:

```js
for (let x = 20; x < width; x += 40) {
  circle(x, 100, 20);
}
```

`draw()` repeats something across time:

```js
function draw() {
  circle(100, 100, 20);
}
```

This is a useful comparison because the idea of repetition is already familiar.

But there is an important difference.

If exactly the same thing happens every frame, nothing appears to change.

Something needs to carry a different value from one frame to the next.

That is where **state** becomes important.

## State is probably the key idea

Animation can easily become a collection of tricks:

- move this
- rotate that
- make this pulse
- change the colour

I think it is more useful to frame it through state.

If:

```js
let x = 100;
```

and later:

```js
x = x + 1;
```

then the system remembers something about its previous moment.

A simple formulation is:

**current state → rule → next state**

That idea is going to matter much more later than the particular animation technique.

It connects directly to:

- behaviour
- agents
- interaction
- feedback
- simulations
- games
- cellular systems

So I would keep coming back to:

> What information needs to survive from one frame to the next?

## Motion is not the same as time

This distinction is worth discussing.

A moving object makes time visible, but movement and time aren't the same thing.

A program can communicate time through:

- movement
- accumulation
- disappearance
- repetition
- changing density
- colour
- events
- rhythm
- waiting

Something could remain almost completely still and still be strongly time-based.

For example, one mark could appear every minute.

Or an image could become gradually darker over several hours.

So I wouldn't let the session become only:

> How do I animate objects?

The more interesting question is:

> **How can a system make change or duration perceptible?**

## `frameCount`, `millis()` and actual time

There are a few different notions of time in p5.js, and I think it helps to keep them conceptually separate.

### `frameCount`

This is really the age of the animation measured in frames.

It is simple and useful for experimentation.

But it is tied to the frame rate.

### `millis()`

This gives elapsed time since the sketch started.

Now we are measuring actual duration rather than the number of frames that happened.

### `second()`, `minute()`, `hour()`

These connect the sketch to an external clock.

The program is no longer only producing its own internal timeline.

It is responding to time outside itself.

I wouldn't introduce all of these immediately.

Start with a changing variable, then `frameCount`, then cycles. Bring in real-world time when moving toward the clock exercise.

## Cycles and oscillation

A value does not always need to increase forever.

This is where `sin()` becomes useful.

I don't think this needs a mathematical lecture.

The useful thing to understand is simply that sine gives us a value that moves back and forth continuously.

Something like:

```text
increase → maximum → decrease → minimum → increase...
```

This can control almost anything:

- x position
- y position
- size
- rotation
- opacity
- spacing
- colour

The important parameters are probably:

- speed
- range
- phase

I would change these one at a time and keep the visual example very simple.

## John Whitney: movement is part of the composition

Whitney works well as the first reference because motion isn't being added to an already designed image.

The moving relationships are the work.

In _Arabesque_, repeated forms, rotation, symmetry and mathematical relationships continuously create new visual states.

I would show a short section of the film rather than only a still.

Ask:

- What is actually changing?
- Which movements repeat?
- Which movements seem connected?
- Is there a single main object?
- Could one frame represent the work?

That last question is useful.

A still can document the system, but it cannot really describe the temporal relationships.

This is one of the first moments in the course where the work doesn't exist completely in a single output.

## Lissajous figures: complexity from related cycles

Lissajous figures are useful because the mechanism is extremely small.

One cycle controls `x`.

Another controls `y`.

```js
let x = sin(t);
let y = sin(t * 2);
```

Neither movement is particularly interesting alone.

The interesting form comes from their relationship.

This is a nice continuation of Session 2:

> Complexity doesn't necessarily come from adding more elements.

Sometimes it comes from combining two very simple rules.

Try different frequency relationships:

```text
1 : 1
1 : 2
2 : 3
3 : 4
```

I would avoid spending too much time explaining ratios mathematically.

Change them and look.

The visual behaviour makes the idea fairly clear.

## Steve Reich: repetition becomes phase

_Piano Phase_ is probably one of the most useful references in this session.

Two performers begin with the same repeating pattern.

Then one becomes slightly faster.

Nothing new is added.

The complexity comes entirely from a small difference in speed.

So:

**same pattern + slightly different tempo = changing relationship**

This is a really strong generative idea.

I would listen to a short part of the piece and use Alexander Chen's visualisation if useful.

Ask:

- When are the systems together?
- When do they feel most different?
- Does either performer explicitly create the resulting intermediate patterns?
- Where does the complexity come from?

Then translate the idea visually.

For example:

```js
let a = sin(frameCount * 0.05);
let b = sin(frameCount * 0.052);
```

Two nearly identical values slowly drift apart and eventually meet again.

This also introduces **phase** without needing to define it too heavily.

## Accumulation: when the past stays visible

One of the simplest but most useful demonstrations is removing `background()` from `draw()`.

Normally:

```text
frame replaces frame
```

Without clearing:

```text
frame + previous frames = trace
```

Now movement becomes drawing.

This is also a good bridge toward Session 4 and the drawing machines.

The important question is:

> **What should the system remember?**

A fully cleared background remembers nothing visually.

No background remembers everything.

A transparent background can sit somewhere between the two.

I would experiment with those three states.

## LIA: the image as history

LIA is useful here because the image often grows through repeated computational actions.

The work isn't only about where something is moving.

It is also about what remains from the movement.

That makes it possible to talk about:

- traces
- density
- history
- accumulation
- transformation

Ask:

> If we only saw the last frame, what information about the process would still be visible?

This idea becomes important in drawing machines, agent systems and later generative processes.

A final image can be a record of a behaviour.

## Tatsuo Miyajima: many times at once

Miyajima is useful because he breaks the idea that one work needs one clock.

In _Keep Changing, Connect with Everything, Continue Forever_, many counters run at different speeds.

Each one has its own rhythm.

Some systems are also connected to others.

I would ask:

> **Is there one time in this work?**

Probably not.

There are many simultaneous temporal systems.

This moves us toward Session 4 because individual elements begin to have their own state and rhythm.

At some point, repetition starts to look like behaviour.

## The references as a progression

I think I would use the references roughly like this:

1. **John Whitney - motion as a designed system**
2. **Lissajous - combine simple cycles**
3. **Steve Reich - rhythm and phase**
4. **LIA - accumulation and traces**
5. **Tatsuo Miyajima - many simultaneous temporal systems**
6. **Clock references - time as input and subject**

I wouldn't spend equal time on all of them.

The point isn't to give a history of time-based art.

The references should gradually open up the definition of what change over time can mean.

## The clock as a case study

The clock is useful, but I would introduce it fairly late.

By then we already have:

- continuous change
- cycles
- phase
- events
- accumulation
- multiple rhythms

The clock becomes a way to connect those ideas to actual time.

The main prompt is not:

> Make an analog clock.

It is:

> **Design a system that communicates time or the passage of time.**

This leaves much more space.

A clock might:

- accumulate
- decay
- reveal only seconds
- ignore seconds completely
- show approximate time
- become less readable
- use several cycles
- translate time into something other than position

The `clock.md` page is there to open this up further.

## Common difficulties

### Everything moves

When every property changes continuously, the system becomes difficult to read.

Ask:

> What could remain constant?

Movement becomes more visible when something else stays stable.

### Animation is added without a reason

Ask:

> What does this change communicate?

Not every element needs to move simply because `draw()` exists.

### `sin()` feels mysterious

Don't begin with the formula.

Plot or print the changing value.

Then map it to a circle moving up and down.

The cycle is easier to understand visually.

### Too many time systems appear at once

Return to one changing value.

Then one cycle.

Then add another relationship.

### The clock immediately becomes a normal clock

Remove the clock face.

Ask:

> What information actually needs to be communicated?

Maybe hours don't matter.

Maybe exact readability isn't important.

Maybe the system is about duration rather than timekeeping.

### `frameCount` is confused with real time

Slow the frame rate or pause the sketch.

Then compare it with `millis()`.

The difference becomes easier to see.

## First use of AI: EXPLAIN

This is also the first session where AI enters the course.

I think that should be quite explicit.

For the first two sessions, the point was to experience the rules and code directly.

Now AI can help explain something that isn't understood.

For example:

- Why isn't this variable changing?
- What does `frameCount` actually contain?
- Why does this jump instead of moving smoothly?
- What range does `sin()` return?
- What does this error message mean?

The useful distinction is:

**AI solves the problem**

versus:

**AI helps me understand the problem**

For this session, stay on the second side.

A good habit is to describe the problem before asking:

> I expected this to happen, but this happened instead.

That already forces some debugging to happen before AI answers.

## Connection to Session 4

Session 3 gives a system state and lets that state change over time.

Session 4 adds another step:

> **What if the next change depends on what the system senses or encounters?**

So:

**Session 3**

```text
state → update → state → update
```

becomes:

**Session 4**

```text
state → sense → respond → update
```

This is where movement begins to become behaviour.

The trace experiments from this session also lead naturally into drawing machines.

## Connection to later AI work

There is another useful connection here.

Generative media systems also operate over time, especially once we work with video and sound.

But even before that, there is a difference between:

**generating one image**

and:

**designing a process that evolves**

I think it is worth keeping this distinction alive.

Later, when AI becomes part of a generative pipeline, we can ask:

- What has state?
- What changes over time?
- What remembers earlier output?
- What triggers the next step?
- Is there a cycle?
- Where is feedback happening?

These questions are much more useful than thinking of AI only as something that produces isolated outputs.

## Sources worth keeping open during class

- John Whitney, _Arabesque_
- Whitney Museum: _Histories of the Digital Now_
- Lissajous references
- Steve Reich, _Piano Phase_
- Alexander Chen, _Piano Phase_
- LIA
- Tatsuo Miyajima
- p5.js reference for `sin()`, `frameCount`, `millis()`, `second()`, `minute()` and `hour()`
- the clock reference page

The detailed links are collected in `examples.md` and `clock.md`.