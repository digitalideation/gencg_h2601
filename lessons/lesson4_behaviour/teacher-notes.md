# Teacher Notes: Session 4 - Behaviour & Agency

These notes are background for Session 4, with teaching prompts and a few possible directions. They can also be shared with anyone who wants to go a bit deeper.

## Why this session exists

Session 3 introduced state and change over time.

A circle moving across the screen already has state:

- position
- direction
- speed

But if it simply continues forever in the same direction, I wouldn't really call that behaviour yet.

The important shift in this session is:

> **What happens when the next action depends on the current situation?**

For example:

```text
move
↓
reach edge
↓
change direction
↓
continue
```

Now the system responds.

I think the session should move through something like:

**state → movement → sensing → response → feedback → multiple agents → emergence**

The drawing machine can then become a case study where these behaviours leave visible traces.

## From movement to behaviour

I would begin with the simplest possible contrast.

First:

```js
x = x + 2;
```

The object moves.

Then:

```js
if (x > width) {
  speed = -speed;
}
```

Now something in the environment changes what happens next.

That difference is small in code but quite important conceptually.

A useful formulation is:

**movement**

```text
state → update
```

**behaviour**

```text
state + situation → response → new state
```

I wouldn't worry too much about creating a perfect definition of behaviour.

The point is to notice when a system starts responding rather than only executing a fixed sequence.

## State, sensing and action

I think these three ideas are enough to build quite a lot.

### State

What does the element currently know?

For example:

- position
- velocity
- direction
- age
- size

### Sensing

What information can affect it?

For example:

- a boundary
- the mouse
- another element
- a trail
- distance
- time

"Sensing" doesn't need to mean a realistic sensor.

It is simply information that becomes available to a rule.

### Action

What can change?

For example:

- position
- direction
- speed
- colour
- size
- whether a mark is made

The basic loop becomes:

```text
sense → respond → update → sense again
```

This is probably enough structure for the first half of the session.

## Feedback

Feedback is an important concept here, but I would introduce it through something concrete.

A boundary bounce is already a tiny feedback loop:

```text
position
↓
boundary detected
↓
velocity changes
↓
new position
```

Then show a stronger example:

```text
agent moves
↓
agent leaves a trail
↓
trail changes the environment
↓
agent responds to trail
↓
movement changes
```

Now the system is partly responding to its own history.

A useful distinction is:

**response**

> input changes output

**feedback**

> output changes future input

This is going to matter later in more complex generative systems as well.

## Generative Design P_2_2: a practical backbone

The P_2_2 examples from _Generative Design / Generative Gestaltung_ are almost perfect for this session.

I wouldn't treat them as one example.

They work better as a sequence.

### P_2_2_1: simple wandering

The code describes it as a "stupid agent", which is actually useful.

It has a position and chooses between possible directions.

That is enough to create a path.

Ask:

> What does this agent actually know?

Almost nothing.

Still, when we watch the trace, it starts to feel like something has happened.

### P_2_2_2: more directed behaviour

Now there are boundaries and directional decisions.

The behaviour becomes less arbitrary.

This is a good place to identify:

- state
- condition
- response

### P_2_2_3: connected agents

Several points move, but they also belong to one larger form.

This is where individual behaviour and collective structure begin to meet.

Ask:

> Is the shape designed directly?

Not really.

It emerges from the positions of several changing points.

### P_2_2_4: aggregation

The diffusion aggregation example changes the logic again.

New elements respond to what already exists.

The structure literally changes the space available for future growth.

That is feedback.

### P_2_2_5: packing

Circle packing is another very clear example.

Every new circle changes what can happen next.

The system develops its own constraints while it runs.

### P_2_2_6: pendulums and traces

This connects directly back to Session 3.

Several linked cyclical movements produce traces.

It is also a good bridge into drawing machines.

A useful code-reading sequence across all of these examples is:

**identify state → identify sensing → identify rule → identify action → change one relationship**

## Braitenberg Vehicles: when simple behaviour looks intentional

I think Braitenberg is probably the most important conceptual reference in this session.

The vehicles are extremely simple.

A vehicle might have:

- two sensors
- two motors
- a light source

Changing how the sensors connect to the motors creates very different movements.

And very quickly we start describing them with words like:

- afraid
- aggressive
- curious
- attracted
- hesitant

The mechanism itself hasn't suddenly become psychologically complicated.

The interesting thing is what **we project onto the behaviour**.

Ask:

> **When do we start seeing intention?**

This will become useful much later when working with AI.

Systems can appear purposeful, social or intelligent without those words necessarily describing what is actually happening internally.

I wouldn't make the AI connection too large yet, but it is worth planting the question.

## Craig Reynolds: local rules and collective behaviour

Boids is the clearest example for moving from one agent to many.

The classic three relationships are:

- separation
- alignment
- cohesion

What matters is that none of those rules says:

> Form a flock.

Each agent only responds locally.

The flock appears at another level.

This gives us:

**local behaviour → interaction → global behaviour**

Ask:

> **Where is the flock stored?**

There is no flock object containing the final composition.

There are only agents responding to nearby agents.

That is emergence.

I would avoid implementing a full Boids system immediately. It is easy for the code to become the whole lesson.

Instead, implement one local relationship first.

For example:

> If another element comes too close, move away.

Then maybe add alignment.

The point is to experience how two rules interact.

## Conway's Game of Life: agency without movement

Game of Life is useful because it breaks the assumption that agents need to move around.

A cell has almost no information:

- alive or dead
- number of living neighbours

Yet repeated local updates can create:

- stable patterns
- oscillators
- moving structures
- growth
- collapse

Ask:

> **What is actually moving in a glider?**

No cell travels across the grid.

Individual cells switch states and the pattern appears to move.

This is a nice example of how behaviour can exist at a level different from the individual element.

I wouldn't turn this into a cellular automata lesson.

It is there to expand the idea of emergence.

## Emergence

This word can become vague quite quickly, so I would keep it practical.

Something is interestingly emergent when the larger result isn't explicitly described by the local rule.

For example:

```text
avoid nearby neighbours
+
align with nearby neighbours
+
move toward nearby neighbours
```

does not contain the instruction:

```text
look like a flock
```

The flock is an outcome of the relationships.

A useful question is:

> **What appears at the global level that isn't explicitly present at the local level?**

This also connects back to 10 PRINT.

The maze-like structure wasn't contained in any individual slash.

So emergence isn't actually a completely new idea in Session 4.

We have already been approaching it since Session 2.

## Jean Tinguely: when the machine has character

Tinguely is a good point to move from behaviour toward drawing machines.

Traditional machines tend to suggest:

- precision
- repeatability
- control
- efficiency

Tinguely's Méta-Matics do almost the opposite.

They shake, wobble and produce unstable marks.

The machine contributes something recognizable to the drawing.

I think the useful question is:

> **What makes a machine feel like it has character?**

It doesn't need personality in a literal sense.

Character can come from:

- delay
- instability
- limitation
- repetition
- error
- overshooting
- friction
- randomness
- refusal

This is a much more interesting direction than simply making a digital pen follow the mouse.

## Drawing machines as a case study

Like the clock in Session 3, I wouldn't make Drawing Machines the whole lesson.

It is one place where the concepts become visible.

The useful shift is:

**draw the image**

to:

**design something that draws**

A drawing machine might respond to:

- input
- boundaries
- previous marks
- another agent
- time
- sound
- environmental data

And its behaviour becomes visible through a trace.

This gives a simple relationship:

```text
rule → behaviour → movement → trace → drawing
```

The separate `drawing-machines.md` page can carry the deeper references.

I would keep the main session focused on behaviour.

## From function to character

This could be a useful short exercise or discussion.

Start with something functional:

> A circle follows the mouse.

Then change one relationship.

For example:

### Delay

The circle follows slowly.

Now it feels heavier.

### Overshoot

It moves past the target and comes back.

Now it feels unstable.

### Noise

Its direction fluctuates slightly.

Now it might feel nervous.

### Refusal

Sometimes it doesn't respond.

Now it might feel stubborn.

The point isn't to anthropomorphise everything.

The point is to see how a small computational relationship changes our reading of behaviour.

A good question is:

> **What rule creates the character?**

If the answer is only a story added afterwards, the behaviour probably isn't doing enough yet.

## Randomness is not behaviour

This is probably one of the main things to watch.

A particle moving randomly is easy to make.

But random movement alone doesn't necessarily create interesting behaviour.

Ask:

> What is it responding to?

Then introduce randomness **inside** a rule.

For example:

```text
when boundary is reached
→ choose a new direction within this range
```

That is different from:

```text
choose a completely new direction every frame
```

As in Session 2, randomness becomes more meaningful when it operates inside a structure.

## One agent before many

There is always a temptation to start with fifty particles.

I would resist that.

If one element's behaviour isn't understandable, fifty copies usually just hide the problem.

Start with one.

Ask:

- What does it know?
- What can it sense?
- What makes it change?
- What happens at an edge?

Then duplicate it.

The collective behaviour becomes much easier to read when the local behaviour is already understood.

## Common difficulties

### Movement is confused with behaviour

Ask:

> What makes the movement change?

If the answer is just "time passes", add a condition or relationship.

### Everything is random

Remove the randomness temporarily.

What rule remains?

Then reintroduce variation somewhere specific.

### Too many agents too early

Return to one element.

Make its behaviour readable first.

### The rules become complicated immediately

Use:

```text
sense one thing
↓
do one thing
```

Then add another relationship only when the first one is clear.

### The behaviour has a story but no computational basis

If the description says:

> This agent is shy.

ask:

> What does shy mean in the rules?

Maybe:

> when another agent is within 80 pixels, move away.

Now the character is implemented.

### The drawing machine becomes an effects generator

Ask:

> What is the machine actually doing?

Try describing the mechanism without describing its appearance.

### The final output becomes more important than the system

Run the same system several times.

Compare the outputs.

Ask:

> What stays recognisable across all of them?

That is probably closer to the identity of the machine.

## AI: from EXPLAIN to COLLABORATE

I think this session is a good place to make the first small transition toward collaboration with AI.

Start in **🟠 EXPLAIN** mode.

Build the first behaviour directly.

Understand:

- state
- movement
- condition
- response

Then, once there is a meaningful working version, AI can become more collaborative.

For example:

- Why does this agent sometimes get stuck?
- Can you explain another way to calculate this distance?
- How could I restructure this code without changing the behaviour?
- I want the movement to feel more hesitant. What kinds of rules could produce that?
- How can I create several agents without repeating all this code?

The important thing is that there is already something to collaborate **on**.

Otherwise the process becomes:

> Describe the desired result → receive a complete agent system.

That skips most of what the session is trying to teach.

A useful question before asking AI is:

> **What rules currently control my system?**

If that can't be explained yet, stay in EXPLAIN mode a bit longer.

## Connection to Session 5

Session 4 introduces systems that can have many interacting values:

- speed
- turning rate
- perception distance
- probability
- number of agents
- attraction strength
- repulsion strength

These naturally lead into Session 5.

Instead of changing them casually, we can start asking:

> **What space of possible behaviours exists inside these parameters?**

So:

**Session 4**

> design behaviour

becomes:

**Session 5**

> explore families of behaviour

This is where parameter spaces become useful.

## Connection to later AI work

Behaviour and agency are also good concepts to keep around once AI enters more strongly.

There will be a temptation to call every AI system an "agent".

I think this session gives us a more concrete vocabulary first.

Ask:

- What state does the system have?
- What information can it receive?
- What actions can it take?
- What changes because of those actions?
- Is there feedback?
- Does it remember?
- Is it actually autonomous?
- Where are decisions happening?

These questions are more useful than assuming agency because a system produces convincing behaviour.

## Sources worth keeping open during class

- _Generative Design / Generative Gestaltung_, P_2_2
- Generative Design p5.js code package
- Valentino Braitenberg, _Vehicles_
- Craig Reynolds, Boids
- Conway's Game of Life
- Museum Tinguely, Méta-Matics
- the Drawing Machines reference page
- p5.js reference

The detailed links are collected in `examples.md` and `drawing-machines.md`.