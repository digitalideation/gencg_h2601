# Teacher Notes: Session 6 - Images as Data
These notes give some background for Session 6, with questions, teaching prompts and a few possible directions. They can also be read after the session, alongside the examples and practical work.

## Why this session exists
In Session 5 we chose values that controlled a system. Here we change where some of those values come from. Instead of typing a size or choosing a colour ourselves, we read information from an image and decide what it should control.

I think that is the useful starting point. This is not a completely separate course in image processing. We already have loops, parameters, drawing functions and perhaps a small drawing machine. Now another source can supply their inputs.  
**image → sample → value → mapping → output**

The question underneath the session is: **What happens when we stop treating an image as a finished picture?**

## Start with the image, not the array
I would look at the source before opening the code. What makes it worth using? Maybe it has strong light-dark differences, a limited palette, repeated textures or a familiar subject that will become less recognisable.

A small mapping diagram is enough to begin. For example, dark areas could produce larger marks. It doesn't need to predict every detail of the final image. It should make the intended relationship clear.

An exported sketch from an earlier session is also a good source. There is no need to find a new photograph every time. Using our own output makes the idea of a pipeline quite concrete: one system produces material for another.

## Kensuke Koike: keep the rule visible
I would open with a physical transformation rather than a software effect. Koike's collaboration with Thomas Sauvin, _No More, No Less_, works with a constraint of adding and removing no material. Their [project account](https://www.lensculture.com/articles/kensuke-koike-and-thomas-sauvin-the-necessity-of-collaboration-in-kensuke-koike-and-thomas-sauvin-s-no-more-no-less) gives us a way to discuss changing relationships while keeping the pieces.

We can try a small paper version, or simply describe one possible rearrangement. Which parts move? Does the rule depend on knowing what the photograph shows? Could the same rule operate on another image?

This brings Session 1 back into the discussion. We are still designing instructions. The material being instructed is different.

## Sampling is already a decision
I would make the first reconstruction quite plain: coloured rectangles at regularly spaced sample positions. That gives us a version we can understand before adding another drawing rule.

Then change only the sampling distance. What disappears first? Does the image remain readable from farther away? A low-resolution result is not automatically less useful; it may reveal a structure that was harder to notice in the original.

There is one detail worth saying out loud: the starter reads one pixel for each cell. It does not calculate the cell's average colour. A small feature can fall between sample positions and disappear. That is a consequence of the sampling rule, not necessarily a broken program.

## Aram Bartholl and HYBE: separate data from display
[Aram Bartholl's 0,16](https://arambartholl.com/016/) makes pixelation physical through a structure of frames, paper and light. [HYBE's IRIS](https://vimeo.com/50200308) uses liquid-crystal elements that change how much ambient light passes through them.

I would use these as two ways of asking what displays a value. A sample is information; a square, circle, aperture or line is one way to make that information visible. We should not assume that the coloured square is the only possible representation.

That distinction leads quite naturally to the practical work. Keep the sample and change the mark. Then ask what that change communicates.

## Keep the first image small
A static image is enough for the core session. Webcam input adds a moving source, browser permissions and more things to debug at once. It can wait.

The starter fits a working image inside 640 × 480 while keeping its proportions approximately unchanged, apart from rounding to whole pixels. The canvas then uses the working image's dimensions. This keeps the source and drawing coordinates aligned. It also means we can discuss mapping without solving a separate scaling problem first.

Resizing happens in memory; it does not overwrite the original file. Keep that original for the journal. If a later version samples the original at one size and displays it at another, the coordinates need an explicit mapping too. See the [p5.Image resize reference](https://p5js.org/reference/p5.Image/resize/).

## Loading is part of the setup, not the main concept
The README uses the p5.js 2.x pattern, `async function setup()` with `await loadImage(...)`. The [current loading reference](https://p5js.org/reference/p5/loadImage/) explains this syntax. The important point for now is simply to wait until the image exists before asking for its dimensions or colours.

Some book examples use `preload()` with p5.js 1.x. I would keep those versions distinct rather than mix their loading patterns in one sketch. There is no need to teach asynchronous programming in depth today, but the example should match the version being used.

For local work, the image path is relative to the page running the sketch. The starter expects `source.jpg` next to `index.html`. Check the real extension and letter case, and use Live Server. A missing file is not a reason to rewrite the transformation.

## Reading a colour is not recognising a subject
A sample gives us channel values at a position. Our small program does not know that this position is an eye, a leaf or a shadow.

That matters when describing the work. "Dark samples make larger marks" is an implemented relationship. "The program understands the face" would be a different claim.

I think this will be useful again in Session 7. A learned image model and a hand-written sampling rule do not use the source in the same way. We should be able to explain this simpler process before comparing it with another one.

## A light-dark value needs a definition
The starter averages red, green and blue to get a simple tone estimate. That is easy to follow, but it is not a precise measure of perceived brightness. Three very different colours can have the same channel average.

I would test the mapping with black, grey and white first. On a white background, a larger black mark makes an area appear darker. Does the code follow that direction? What happens when we reverse it?

Keep the background and mark colour visible in the explanation. "Bright means large" is not universally right or wrong. It depends on what the output is supposed to do.

## Generative Design: follow the value through the code
[P_4_3_1_01](https://github.com/generative-design/Code-Package-p5.js/blob/master/01_P/P_4_3_1_01/sketch.js) is useful because one source supports several representations. I would compare two modes, not tour all nine. A line-weight version and a coloured-circle version are enough to begin a discussion.

Trace one sample through the program: where is it read, how is it reduced to a number, and where does that number reach a drawing command? Which controls come from the mouse instead?

There is also a useful implementation detail in the supplied code: it calls `img.loadPixels()` inside the nested loop. We do not need to repeat that pattern. For the direct-array extension, load the source pixels once before the loop. Keep the visual idea separate from the implementation choices we might improve.

## Mapping, rearrangement and accumulation
I would not use "filter" for every operation. It hides differences that are useful to understand.

Mapping changes what a value controls. Rearrangement changes where samples or fragments appear. Accumulation lets marks build a result over time. One program can do several of these things, but naming the first operation keeps the idea manageable.

[Pixel is Data](https://apps.apple.com/us/app/pixel-is-data/id622378844) is useful here because it questions photographic order as the only arrangement. [Kim Asendorf's sorting code](https://github.com/kimasendorf/ASDFPixelSort) gives us a more explicit implementation to inspect. His [100.000.000 Stolen Pixels](https://kimasendorf.com/100000000/) opens another scale: fragments from many images become a collection with several possible arrangements.

These are references, not a requirement to build a sorting system or a crawler. One row of samples is enough to test the difference between preserving values and preserving positions.

## Two comparisons, not more effects
I think the comparison is the most important part of the independent work.

First, keep the source and change one mapping or parameter. Then keep a configuration and change the source. Those answer different questions. The first helps us understand the rule; the second helps us understand its relationship to the material.

Keep dimensions and other settings comparable where possible. If they differ, record that. If a drawing accumulates over time, compare captures after the same duration or number of steps. If randomness matters, keep its sequence stable while testing another decision.

The aim is not a perfect scientific experiment. It is to avoid changing everything at once and then guessing what caused the result.

## One transformation is enough
It is tempting to add pixel sorting, a webcam, particles, sound and a 3D surface. I would keep those as possible directions on the examples page, not as separate exercises.

Someone can reuse the module from Session 5. Someone else can give an existing drawing machine a sample to respond to. The useful question is whether the input, mapping and output can be explained.

A result can be simple and still make an interesting decision about the source. Making the photograph unrecognisable is not automatically a failure, just as preserving it perfectly is not automatically the goal.

## AI: inspect the rule before extending the program
This session stays in **🟡 COLLABORATE**. There should be a mapping sketch and a first attempt before asking AI to change the implementation.

A useful request is: "Darker samples should produce larger marks. Does this code follow that rule? Explain any mismatch and suggest the smallest change."

Then test the answer. Use known sample values, not only a visually complicated image. If AI makes the code faster, compare the output before and after too. A faster result is not necessarily an equivalent one.

Code and a few numerical examples are often enough for this discussion. We do not need to upload the source photograph just to investigate an indexing mistake. A partner can also review the same relationship when AI is not used.

## Common difficulties
### The image does not load
Check the path, extension, letter case, local server and network error first. The problem may have nothing to do with the sampling code. Avoid remote image URLs for the starter; browser security can block them.

### The samples seem to come from the wrong place
Use `img.get(x, y)` to read the source. Plain `get(x, y)` reads the canvas. Also check whether image and canvas coordinates are being mixed after scaling.

### The result becomes very slow
Increase the sampling step and use a smaller working image. Do not redraw a static study every frame. Once the mapping is clear, consider the direct pixel array.

### There are stripes or unexpected colours
For direct indexing, check the source width, the four RGBA entries per pixel and the image pixel density. Do not sort red, green and blue entries independently when the intention is to move whole colour samples.

### Transparent regions behave strangely
Start with an opaque image. Transparent PNGs contain alpha as well as colour; their stored RGB values may not match the background they appear on. Handling transparency is another decision, not something the starter tries to hide.

### There is a nice result but no clear explanation
Return to one sample. Which value was read, which rule used it, and what was drawn? A small diagram can reveal what a long description misses.

## Useful vocabulary
**Source** is the input image. **Sample** is a value read at a chosen location. **Channel** is one component such as red or alpha. **Mapping** connects an input value to an output property. **Reconstruction** keeps some spatial relationship to the source. **Rearrangement** changes that relationship. **Feedback** happens when output affects later input.

These words help describe a process. They are not requirements to include every technique in one sketch.

## A possible rhythm
For 150 minutes, I would try 15 minutes for source images and references, 25 for loading and sampling, 25 for the first mapping, a 10-minute break, 45 for development and the two comparisons, 15 for feedback, and 15 for sharing and exporting.

That is one developing system, not seven assignments. If setup takes longer, shorten the extensions rather than lose the comparison with a second source.

## What the journal should make visible
Keep both sources, the mapping diagram, a coarse reconstruction and the comparisons together. Label what changed. Add the exported result and enough settings to find the same configuration again.

A few sentences can explain why the image was chosen, what the transformation keeps or removes, and whether feedback changed the decision. There is no need for a long account of every line of code.

## Connection to generative media
Exporting a result gives us a concrete next step. A p5.js image can become input to another process, including a generative image model later on.

I would not start that model work here. First we need a transformation whose decisions we can inspect. In Session 7 we can compare what our code specifies with what a learned model supplies.

The question continues to be: **What comes from the input, what comes from the system, and what did we decide ourselves?**

## Sources worth keeping open during class
- [Kensuke Koike - Nothing Added, Nothing Removed](https://www.lensculture.com/articles/kensuke-koike-nothing-added-nothing-removed)
- [Aram Bartholl - 0,16](https://arambartholl.com/016/)
- [Generative Design - P_4_3_1_01](https://github.com/generative-design/Code-Package-p5.js/tree/master/01_P/P_4_3_1_01)
- [Matthieu Savary - Pixel is Data](https://apps.apple.com/us/app/pixel-is-data/id622378844)
- [Kim Asendorf - ASDF Pixel Sort](https://github.com/kimasendorf/ASDFPixelSort)
- [HYBE - IRIS](https://vimeo.com/50200308)
- [p5.js - image loading](https://p5js.org/reference/p5/loadImage/)
- [p5.js - reading image samples](https://p5js.org/reference/p5.Image/get/)

→ [Examples and references](./examples.md)  
→ [Back to Session 6](./README.md)
