# Teacher Notes: Session 8 - Hybrid Pipelines

These notes describe a possible **150-minute individual workshop**. The exercise is about creative decisions across systems, not learning a new API.

## Why this session exists

In Session 7 students treated an image model as creative material and compared what it preserved or changed.

Now we want to see what happens when **several systems contribute to one work**:

**AI image → p5.js reconstruction → coded variation → AI reinterpretation**

The first model offers an image whose underlying rules are not directly editable. In p5.js, students invent a simple set of explicit rules that could produce a related composition. Then they modify those rules and bring the result back to a model, which adds a different form of interpretation.

A manual PNG transfer makes the transitions clear. We do **not** need API integrations to investigate this.

## What is out of scope

- no Replicate API calls, Node.js, npm or custom proxy
- no training models or custom LoRA work
- no requirement for exact image reconstruction
- no polished final artwork or mandatory animation
- no fixed style for the final output

Students work individually throughout. Whole-class sharing is optional.

## Inspiration before instruction

I would open with two references rather than a long lecture:

**Mark Webster, Neural Drawings.** Algorithmic drawing moves through neural transformation and physical printing. Ask: **Why combine several systems instead of making a final image with one tool?** His software is custom, so do not call it a p5.js example.

**JCode, What Remains (2026).** The artist describes photographs transformed using p5.js and then a custom LoRA image model. Ask: **What does the code stage do that a direct image-editing prompt would not?** The source project concerns conflict and should be introduced with care. For the class, students use their own abstract or nonsensitive images.

**Botto, Algorithmic Evolution** is an optional third reference. AI-generated p5.js code and iterative selection make the code itself part of the creative output. It is not the same setup as our manual pipeline.

**Surya Narreddi's Training AI to Paint with Code** is another optional reference for AI producing JavaScript instructions rather than a finished image.

The artist pages and discussion questions are in [examples.md](./examples.md).

## Choosing a manageable starting image

Students should generate or select a composition with **clear visual relationships**. For example:

> A flat minimal composition of seven black circles along a diagonal, gradually increasing in size. Off-white background, no shadows, no text.

Ask which rules could produce it: number, spacing, position, size progression. A small grid or repeating symbol also works.

If a student starts with a complicated photorealistic scene, ask them to reduce it to its most distinctive relationship. Complexity is not the goal. Students may reuse an image from Session 7 if it is easy enough to interpret.

Prepare a couple of simple starting images in advance in case Replicate access is unavailable.

## Reconstructing is not tracing

The model did not secretly run a p5.js sketch that students must recover. We are asking them to **invent an understandable rule-based equivalent**.

A short loop that captures repetition or a simple function that controls spacing is better than a large codebase they cannot change.

The course is now in **🟢 OPEN** mode. Students can use an LLM to help write or debug code, but each should be able to identify and change the important rules. If the code is too complex to explain, simplify it.

## The most important transition

The step from **p5.js reconstruction to coded variation** is the conceptual centre of the workshop.

A purely cosmetic adjustment is not quite enough. Encourage students to change the system: repetition, density, spacing, branching, hierarchy, connectivity, growth or controlled randomness.

A useful question is:

> What can you control in the code that was difficult to control with the original image prompt?

This connects naturally to previous sessions about rules, parameters, variation and images as data.

## Returning to the model

The **input for the final model run is the coded variation PNG**, not the original AI image.

Ask students for a new interpretation or context rather than just a beautiful surface treatment. A grid could become a city, a pattern of circles could become islands, or a branching structure could become an organism.

One model result is enough. It does not need to preserve every detail. If the model changes the structure unexpectedly, students can discuss whether that supports or undermines the idea.

## A possible 150-minute rhythm

- **15 min:** Mark Webster and JCode as inspiration; what does each stage contribute?
- **20 min:** generate or choose a simple image and note its visual rules
- **45 min:** reconstruct a manageable version in p5.js
- **10 min:** break
- **20 min:** modify the coded system and export a new PNG
- **25 min:** reinterpret the PNG in Replicate
- **15 min:** assemble and discuss the four stages; short individual reflection

I would rather have four clear stages and one meaningful code change than many visually impressive outputs that the student cannot explain.

## When students get stuck

### The starting image is too complex

Ask for the simplest visual grammar that still captures the idea. A few repeated marks or a size progression is enough.

### AI writes code the student cannot understand

Find one meaningful loop, variable or function and ask the student to change it intentionally. Simplify the code if necessary.

### The coded variation looks almost the same

Focus on a change to spatial relationships, growth, density or repetition rather than palette alone.

### The final model ignores the structure

Compare input and output first. Then ask whether the prompt communicated what should remain. One failure can be more useful than another random generation.

### Tool access becomes the problem

Use prepared image examples or reuse a Session 7 output. The p5.js reconstruction and variation are still useful work. A prepared before-and-after example can help complete the final comparison without a live model run.

## Closing and journal

Each student should leave with:

- four images in chronological order
- the sketch and an identifiable coded change
- the prompts and model names
- a short explanation of what each system contributed

For the closing discussion, ask:

- At which stage was the work most editable?
- When was it most open to surprise?
- What would be lost if you removed one stage?
- How much of the final idea came from the source, the code, the model and the student's selections?

This is a bridge toward final projects. Hybrid systems are one possible direction, **not a requirement**. A fully coded generative work can be equally strong.

## Sources worth keeping open

- [Mark Webster: Neural Drawings interview](https://verse.works/journal/on-neural-drawings-of-mark-webster)
- [Mark Webster: development work](https://mwebster.online/dev/page-3)
- [JCode: artworks and project descriptions](https://www.jcode.art/)
- [Botto: Algorithmic Evolution](https://verse.works/series/algorithmic-evolution-by-botto)
- [Botto: p5.js documentation](https://docs.botto.com/collections/p5.botto)
- [Surya Narreddi: Training AI to Paint with Code](https://surya.website/rling-qwen-to-paint-with-code)
- [FLUX.2 Klein 4B on Replicate](https://replicate.com/black-forest-labs/flux-2-klein-4b)

→ [Student lesson](./README.md)  
→ [Examples and references](./examples.md)
