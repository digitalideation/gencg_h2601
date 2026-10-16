# Teacher Notes: Session 5 - Parameter Spaces
These notes give some background for Session 5, with questions, teaching prompts and a few possible directions. They are also here to read after the session, alongside the examples and the Faces page.

## Why this session exists
We have already been changing values for several sessions. So I don't think the point here is to announce that variables exist, or to add sliders to everything.

The useful change is in how we work. Instead of adjusting values until something looks interesting, we decide which controls matter and compare their effects deliberately. We are designing a family, not only selecting a nice output.  
**existing system → parameters → ranges and relationships → comparison → selection**

I would begin with something that already works. It could be a repeated composition, a temporal system or a drawing machine. That gives us a small checkpoint without turning the whole session into catching up on unfinished work.

## What is different from Session 2?
In Session 2 the useful habit was: change one thing and observe what happens. That still matters. Here we go a bit further and ask what combinations the system allows, which relationships should stay fixed, and how we can return to a result.

A comparison grid also has a different role now. Earlier it organised marks in a composition. Here it can organise experiments. Each cell is another configuration of the same generator.

> **What can change while the system still feels like the same system?**

## A short checkpoint
I would reopen a sketch and explain one relationship before introducing anything new. Which value changes which part of the result? Is that relationship clear in the code, or is the value buried somewhere?

There is no need to finish all the earlier exercises first. Pick something small enough to understand. A complicated agent system with several unresolved problems is probably not the easiest starting point. A simple module with three clear controls is completely fine.

This keeps a useful part of the old reflection session: looking back, choosing what matters and deciding what to continue.

## Parameters are choices, not every variable
A program might contain dozens of variables. That doesn't mean it needs dozens of controls.

In a moving system, `x` and `y` can be state that changes while it runs. A maximum speed or turning range can be a parameter we choose. The same value could play a different role in another program, so I wouldn't make the distinction too rigid.

The question is practical: **What do I want to be able to adjust from outside the construction?** Start with three meaningful parameters. More is not automatically better. One control that changes several related parts can be more useful than ten unrelated sliders.

## Ranges and relationships
A name is only the beginning. A parameter also needs a range or a set of options. It helps to write these on the sketch before building the interface.

For a face, eye spacing could be measured in pixels. Or it could be a fraction of the head width. Those are different design decisions. In the second version, changing the head also changes the spacing. We have designed a relationship, not simply replaced a fixed number.

Continuous and discrete controls are worth separating. Width can change gradually. The number of eyes is a whole-number choice. A shape category is another kind of discrete choice. Linked controls are not a third numerical type: they describe how values depend on one another.

I would test the ends of each range quite early. Is an overlap unwanted, or could it belong to the system? There is no need to force every result into a conventional shape. But there should be a reason for the limits we choose.

## Describe the construction once
The function is the main technical step. We have one construction, and we call it with different settings. This is useful for comparing versions without copying the entire program.

The small module in the README separates placement from design controls. Its centre places it on the page; radius, arm count and dot size change the module. That distinction helps when nine versions need to sit beside one another.

I would keep this at the level of a small named function. There is no need for classes, a configuration framework or a complicated interface library. Someone continuing an existing system can refactor only the part needed for the comparison.

## Make the possibilities visible
The 3 × 3 comparison is probably the centre of this session. One parameter changes across columns, another across rows, and the remaining controls stay fixed. Label the values. Otherwise it becomes a collection of pictures rather than something we can read.

We should also say what the sheet doesn't show. It samples two controls; it is not a complete view of a system with three or more parameters. Another pair of controls gives another view.

A useful question is: **Which region would you investigate next?** Maybe the difference between two nearby settings is more interesting than either endpoint. The first grid can tell us where to look more closely.

For animation, separate captures are enough. Restart from comparable conditions and capture after the same duration. Building nine simultaneous simulations would turn a simple comparison exercise into an infrastructure problem.

## Randomness can hide the comparison
If every adjustment also produces a new random layout, it becomes hard to tell what caused the difference. I would keep the random sequence fixed during the first comparison, then explore different seeds afterwards.

[p5.js `randomSeed()`](https://p5js.org/reference/p5/randomSeed/) gives us a repeatable sequence. It is not a saved image. The code, order of random calls and relevant inputs still matter. In a moving system, resetting the seed every frame changes the process; usually the comparison needs a reset at the beginning of each run.

This is not a demand for perfect scientific reproducibility. It is a way to make our creative decisions easier to understand.

## Max Bill: keeping a common construction
I would use _Fifteen Variations on One Theme_ to open the discussion about families. The work gives us a theme and variations connected by a geometric construction. The [collection documentation](https://www.mercedes-benz.art/en/artwork/quinze-variations-sur-un-meme-theme-15-variations-on-one-theme-max-bill-1935-38-2/) is useful background.

I wouldn't describe this as an early software interface. It is a reference for thinking about what can vary while something recognisable remains. We can ask whether a difference comes from changing a value, changing what is visible, or changing the interpretation of the construction.

## Generative Design: read the controls, not just the output
The two selected examples give us different things to inspect. [P_2_1_1_01](https://github.com/generative-design/Code-Package-p5.js/tree/master/01_P/P_2_1_1_01) separates stroke-weight controls, stroke-cap choices and a random layout. [P_2_2_6_01](https://github.com/generative-design/Code-Package-p5.js/tree/master/01_P/P_2_2_6_01) exposes the number of joints, line length and speed relationship in a linked movement.

We don't need another tour of the whole book. Revisit an example and ask: which controls are independent, which are linked, and what resets when a setting changes? Reading an existing program this way is different from trying to reproduce its appearance.

For the pendulum example, distinguish speed of execution from the shape of a completed trace. A faster process may produce more drawing at a fixed capture time without producing a different completed construction.

## Weird Faces and TYPEFACE
[Matthias Dörfelt's Weird Faces](https://www.mokafolio.de/works/Weird-Faces) is useful because the algorithmic family keeps a personal drawing character. I would ask what appears consistent without pretending that we know the original implementation.

[Mary Huang's TYPEFACE](https://mary-huang.com/projects/typeface/typeface.html) opens another direction: facial dimensions become inputs to type design. We can discuss that mapping without introducing a camera today. Manually chosen values are enough to test the same basic question: what changes, and what must remain readable?

These references should broaden the session. They are not a requirement to build both faces and typography.

## Faces is a case study, not the whole lesson
The old Faces material is worth keeping. It makes parameters and relationships quite immediate. But I would give equal space to someone continuing a drawing machine or abstract system.

The dedicated [Faces page](./faces.md) holds the larger collection. Its tracking, recognition and learned-model projects are references for later exploration, not extra technical requirements for Session 5.

There is also a useful critical question here. A control called "expression" or "age" is not a neutral description of a person. In a stylised drawing it is a mapping we have invented. We should be able to describe the geometry it changes rather than imply that the generator measures identity, personality or emotion.

## The references as a progression
I would start with Max Bill, then use Generative Design to connect the idea to code. Weird Faces and TYPEFACE show how a family can also have a recognisable character or another source of input.

A few examples are enough. The point isn't to add a long history lecture between every practical step. We can return to a reference when a question comes up: what stays fixed, how a control is chosen, or when a variation stops belonging to the family.

## AI as a reviewer of an existing system
Session 5 stays in **🟡 COLLABORATE**. There should be a parameter sketch and a meaningful working version before AI is asked to extend anything. The comparison sheet gives us something concrete to discuss.

A useful request is: "Here are my parameters and their ranges. Identify one relationship I may have overlooked. Explain it without replacing the visual idea."

Then test one suggestion. Did it make the system clearer? Did it remove an interesting possibility? Did it solve a different problem? Rejecting a suggestion can be a good decision. The aim is to practise judgement, not to prove that AI always improves the work. Peer review can serve the same purpose when AI is not used.

If AI helps refactor a function or add a control, compare the behaviour before and after. A tidier program is not automatically an equivalent program.

## Common difficulties
### Everything becomes a slider
Return to the three controls that matter most. The interface should expose a decision, not every implementation detail.

### Each cell is a different program
Keep the same construction and change the settings. If a new rule is needed for each cell, we may be comparing different systems instead of configurations of one system.

### The output changes but the cause is unclear
Hold the other controls, inputs and starting conditions fixed. Change one value, predict the effect, then run it.

### The limits look broken
Check for a technical problem first. Then decide whether the unusual combination should be allowed, constrained or developed further. Unfamiliar is not the same as wrong.

### A favourite result cannot be recovered
Save the values with the image, along with the code version and any relevant seed, input or duration. A preset is a way back to a configuration, not only a name for a screenshot.

### There is too much to build
Use the existing sketch. A function, a labelled comparison and three selected configurations are enough. Sliders and linked controls can remain small extensions.

## Suggested rhythm
For a 150-minute session, I would try: 15 minutes for the checkpoint and references, 25 for parameters and functions, 30 for the comparison grid, a 10-minute break, 45 for development and the feedback comparison, and 25 for sharing and documentation.

That is a working rhythm, not six separate assignments. The same small system should carry through the whole session. If setup takes longer, I would shorten interface work rather than lose the comparison and discussion.

## What the journal should make visible
Keep the diagram, ranges, comparison sheet and three selected configurations together. A few annotations should explain what was tested, what surprised you and why you selected those versions. Include the feedback comparison if it changed the work.

I don't think we need a long reflection after every parameter change. The visual record should already show much of the reasoning. The writing helps connect the decisions.

## Connection to Session 6
For now, we choose the input values ourselves. In Session 6, some of those values can come from an image: a sampled brightness might control size, or a colour might become material for a drawing.

That makes the parameter work useful beyond this session. We have a system with understandable inputs. Next we can ask what happens when another source supplies them.

Later, the same question applies to AI-assisted media. Which controls are explicit? Which relationships come from a model we did not design? A small parametric generator gives us something concrete to compare with, without treating a few named sliders as equivalent to a learned model's internal space.

## Sources worth keeping open during class
- [Max Bill - Fifteen Variations on One Theme](https://www.hauskonstruktiv.ch/en/collection/quinze-variations-sur-un-meme-theme)
- [Generative Design - p5.js code package](https://github.com/generative-design/Code-Package-p5.js)
- [Matthias Dörfelt - Weird Faces](https://www.mokafolio.de/works/Weird-Faces)
- [Mary Huang - TYPEFACE](https://mary-huang.com/projects/typeface/typeface.html)
- [p5.js - createSlider()](https://p5js.org/reference/p5/createSlider/)
- [p5.js - randomSeed()](https://p5js.org/reference/p5/randomSeed/)

→ [Examples and references](./examples.md)  
→ [Faces and parametric generators](./faces.md)  
→ [Back to Session 5](./README.md)
