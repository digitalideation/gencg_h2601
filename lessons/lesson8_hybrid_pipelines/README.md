# Session 8: Hybrid Pipelines

> What becomes possible when an image is the starting point for another creative system, rather than the final result?

In Session 7, we gave images to a model and compared what it changed. Here we will move **between generative AI and generative code**. We will turn part of an AI-generated image into editable p5.js rules, change those rules, and let an image model interpret the new result.

**AI image → p5.js reconstruction → coded variation → AI reinterpretation**

We will transfer PNG images manually between p5.js and the **Replicate web interface**. **No API, Node.js or new software setup is needed.** You will work individually.

## 🟢 OPEN

You can use AI to generate or transform images and to help write or debug code. You should still understand your sketch, modify its important rules yourself and document where your decisions happened.

## What we will explore

By the end of this session, you should be able to:

- identify repetition, spacing, scale, arrangement or other rules in an image
- make a simple p5.js system that interprets those rules
- change that system in a meaningful way
- use an image model to reinterpret the coded result
- explain what each of the four stages contributed

→ [Artists, references and creative directions](./examples.md)

## 1. Choose or generate a starting image

Start with a simple visual idea, such as an invented plant, a set of symbols, a fictional city plan or an abstract pattern.

Open the [FLUX.2 Klein 4B playground](https://replicate.com/black-forest-labs/flux-2-klein-4b) on Replicate and generate an image **from text only**. Leave the **Images** input empty.

Ask for a composition that will be easy to interpret with code: a few shapes, a grid, repeated elements or a clear branching structure. Avoid complex photographs, shadows and busy details for now.

For example:

> A flat minimal composition of seven black circles along a diagonal, gradually increasing in size. Off-white background, no shadows, no text.

Download the image. You can also reuse a simple AI-generated image from Session 7.

**Before coding:** write down two or three visual rules you see. Which one could be interesting to change?

## 2. Reconstruct the rules in p5.js

Open a p5.js sketch, either a new project or something from an earlier session.

Create **an understandable system that could produce a similar composition**. Use shapes, variables, loops, functions, arrays or randomness as needed.

For the seven-circle example, you might use a loop to place seven circles, calculate each position from its index and increase the diameter each time.

**Do not trace the image pixel by pixel.** You do not have to reproduce its details exactly. Simplify it until its important relationships are easy to understand and edit.

If you use an LLM to help with the code, inspect the result. Can you explain what the main loop or variables do?

Export a PNG as **02-reconstruction.png**.

## 3. Change the coded system

Now make **one meaningful change to the rules**, rather than only adjusting the colours. For example:

- change the number of shapes or the rules for their positions
- turn a row or grid into a spiral
- add controlled randomness, growth or branching
- change the rhythm, size progression or connections
- add interaction or motion and export an interesting frame

Compare your new output with the reconstruction. What can you now control precisely that was difficult to specify in the original AI image?

Export your new image as **03-coded-variation.png**.

If you need to export from p5.js, you can use `saveCanvas('03-coded-variation', 'png')` in your sketch, for example when a key is pressed.

## 4. Reinterpret the coded variation with a model

Go back to an image-editing model on Replicate, such as [FLUX.2 Klein 4B](https://replicate.com/black-forest-labs/flux-2-klein-4b).

1. Upload **03-coded-variation.png** under **Images**.
2. Write a prompt that gives the coded composition a new **meaning, material or context**.
3. Say what should stay recognisable and what the model may reinterpret.
4. Run the model and download the result as **04-model-reinterpretation.png**.

For example:

> Use the uploaded pattern of circles as the structure of an imaginary archipelago seen from above. Keep their relative positions and size progression, but reinterpret the circles as islands with coastlines and terrain.

**Upload the changed p5.js image, not the first AI image.** This is a new interpretation of the system you have made, not an attempt to get back to your starting point.

One model result is enough. If the model adds something unexpected, note it rather than endlessly correcting the prompt.

## 5. Compare the four stages

Arrange your four actual images side by side:

| 1. Starting AI image | 2. p5.js reconstruction | 3. Coded variation | 4. AI reinterpretation |
| --- | --- | --- | --- |
| What interested you? | Which rules did you rebuild? | What did you change? | What did the model add? |

Look at the whole sequence and ask:

- When did the image become easier to control?
- What did your code make possible that a prompt alone did not?
- What did the model add that your code did not?
- Would your idea lose anything if you removed one stage?

The aim is **not a polished final artwork**. The process and the reasons for each step are the result.

## What to keep for your journal

Keep one connected record:

- all **four images**, in order and clearly labelled
- your p5.js sketch or a link to its code
- your initial visual rules and the change you made in code
- the model name(s) and prompts you used
- a short reflection about which stage mattered most and why

Save the generated images locally. Use material you made or have permission to upload; avoid private or sensitive images.

## Looking ahead

A hybrid pipeline is one possible direction for a final project, **not a requirement**. A strong project built entirely with p5.js is equally valid. Choose techniques because they support the idea.

→ [Examples and references](./examples.md)  
→ [Teacher notes](./teacher-notes.md)
