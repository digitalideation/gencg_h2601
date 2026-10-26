# Teacher Notes: Session 7 - Generative Media

These notes give some background for Session 7, with questions, teaching prompts and possible directions. They can also be read after class, alongside the examples and practical experiments.

## Why this session exists

This is an important change in the course, and I think it deserves some space.

Until now, we have written the rules that produce the image. Sometimes the code became complicated, but we could still point to a loop, a parameter or a mapping and say what it was doing.

Here we introduce a model whose learned behaviour we cannot describe in the same way.

That doesn't mean creative decisions disappear. It means we have to look for them somewhere else:

**source → intention → model → interpretation → selection**

The aim is not to teach a new application. It is to understand what kind of material a generative model becomes in the creative process.

## Why start with still images?

We could introduce image, sound and video at once, but I wouldn't.

Still images make comparison much easier. We can put the input and outputs next to each other and discuss specific changes in composition, surface and meaning.

This also builds directly on Session 6. We already know that an image can provide data for another system. Here the model uses that image in a different, learned way.

There is no requirement to write p5.js code today. This is deliberate. We are taking time to investigate the model before connecting it to code in Session 8.

## The bridge from Session 1

I like beginning with something almost stupidly simple: two circles or a few lines on a light background.

Describe the rules. Then ask the model to preserve those relationships while changing the material.

For example:

> Keep the two circles where they are. Make them look like objects cut from folded paper.

In Session 1, an instruction was interpreted by another human. Here it is interpreted through a generative model.

Ask: **How much does the instruction actually determine?**

This also gives us a reason not to begin with a complicated illustration. If the input is already crowded, it becomes harder to see what the model contributed.

## The shared demonstration

I would do the first comparison together, perhaps with one source and two runs.

Before showing the output, ask for predictions:

- Which elements will stay in place?
- Will the number of shapes remain correct?
- How might it represent empty space?
- What kinds of details might appear without being requested?

Show the result and compare it with those predictions.

This should be a discussion, not a demonstration of how impressive the model is. A model that invents a third circle gives us something quite concrete to talk about.

Then let everyone work with a source they made themselves.

## Why a series rather than endless prompting?

Generating again can feel like progress, even when we are no longer sure what we are testing.

I think the six-image structure is helpful because it gives the comparison two readable dimensions.

**Three treatments** are enough to see whether a material instruction produces a recognisable family of changes.

**Two models** are enough to notice that the same input can be interpreted differently.

But I wouldn't treat it as a scientific benchmark. Different models have different controls, and the exact conditions may not match. The series is a small design investigation.

The suggested fallback also matters: if everyone cannot access a second model, compare two instruction strategies inside one model and label the difference honestly.

We should not let account problems become the main topic of the class.

## Choosing the models

For the draft I would start with **FLUX.2 Klein 4B** on Replicate. It supports reference-image editing, has a permissive Apache-2.0 licence and exposes inputs we can understand.

FLUX 3 Image could be the contrasting model. It is not an open-source equivalent, and it does not expose exactly the same settings. The `Grounding` setting should be disabled for this particular isolated experiment.

These are teaching choices, not permanent recommendations. Before class, run our actual source image through both models and check that the interaction is understandable, the outputs are useful and the costs are manageable.

If another permissively licensed model is better at that point, change it. The lesson should not depend on a model name.

## Artist references

I would use three references, and not give them equal time.

### Anna Ridler: decisions before generation

Ridler's `Myriad (Tulips)` makes the work of collecting and labelling source images visible. Those images became the dataset for `Mosaic Virus`.

Ask: where is the creative work happening before the generated output exists?

It is a useful corrective to the idea that the model is simply a box we type into.

Our exercise uses a pretrained model. We should be clear that this is a different technical approach, even if the broader questions about sources and choices still connect.

### Sofia Crespo: convincing does not mean true

`Neural Zoo` makes us recognise parts of nature in forms that are not real organisms.

Ask: why does this seem plausible?

This is useful because our models will probably add shadows, textures and physical details to very simple structures. Those details can make an image more convincing without making it more faithful to the original.

### Memo Akten: the model's way of seeing

In `Learning to See`, ordinary material is reconstructed through learned visual worlds.

This probably comes closest to the question we want to investigate: what does the model bring to an image from its own prior training?

I would show the source and interpretation together, not only the attractive output.

The project uses custom models and live video input, so we shouldn't imply that it is technically equivalent to our Replicate editing exercise.

## Keeping the comparison fair enough

The idea is to change only what we are investigating whenever possible.

For the first row, keep:

- the source image
- aspect ratio and output size
- the instruction structure
- other supported settings

Change only the requested treatment.

When switching models, we can't necessarily hold every parameter constant. Document that instead of hiding it.

A seed can help repeat results within models that expose one, but the same seed across two different models is not a meaningful guarantee of visual similarity.

Also, every version should begin from the same original image. Chaining outputs one after another is interesting, but it introduces another variable. That belongs better in Session 8.

## When the result is more polished but less useful

This is probably the most important discussion.

A model can make a simple composition look like a highly produced image. It can add depth, light and material detail very quickly.

But maybe the original was more interesting.

Ask:

> What did the generated image improve for the concept, and what did it flatten or replace?

Keep one result that didn't meet the intention. Rejections are evidence of judgement, not wasted output.

## Training, conditioning and prompting

I would explain these differences briefly when the references make them relevant.

**Training** changes how a model learns from examples.  
**Conditioning or editing** uses a supplied image to influence a generated result without necessarily changing model weights.  
**Prompting** gives textual direction at inference time.  
**Selecting** decides which results become part of the work.

These are different creative actions. We should not call them all "training the AI".

Nor should we describe an editing instruction as a geometrically exact rule. Unless a workflow enforces geometry in another way, it remains something the model may or may not follow.

## Cost, privacy and access

Replicate runs are not automatically free. I would test two models beforehand, estimate the total runs and agree on an acceptable class budget.

For the shared demonstration, use a non-sensitive image prepared in advance. Ask everyone to use their own images or ones they have permission to upload.

Replicate's web predictions are retained until manually deleted, while API predictions have a different default retention policy. This is worth mentioning before uploads, not after. Don't ask for personal photographs as input.

Have a small prepared before/after set ready if accounts, billing or network access fail. A pair can still analyse the same questions using those outputs.

## A possible session rhythm

For a 150-minute session, I would try something like:

- **15 min:** reconnect Session 6 to the new question; shared simple image and predictions
- **20 min:** first model run together; discussion of what changed
- **20 min:** Ridler, Crespo and Akten, selecting just the passages needed
- **10 min:** break
- **45 min:** individual six-image study (or reduced series), saving settings and outputs
- **25 min:** pair comparison, selection and rejection
- **15 min:** share a few findings and connect them to Session 8

This is only a possible rhythm. The important part is to leave enough time after generation to look carefully. I would rather finish with four well-compared images than twelve images nobody has examined.

## Common difficulties

### The session becomes a prompt competition

Return to the source and the initial "Keep / Change" statement. What exactly is being investigated?

### Too many models at once

Choose one for the first experiments. Add the second only when the comparison has a reason.

### The model changes the composition completely

That might be useful evidence. Document which relationship failed rather than simply saying "bad result".

### The source image is too complicated

Reduce it. A few shapes may be easier to investigate than an illustration full of details.

### Random generations are compared as though nothing else changed

Record the seed where available, plus input and settings. Don't assume different models share the same meaning for that seed.

### The selected image is only the most polished one

Ask what it actually preserves of the intended system.

### Everything is framed as "AI did it"

Ask what was decided in the source, prompt, series design, model choice, rejection and selection.

## Bridge to Session 8

Here we use a model to change something we have made.

Next time, I think it would be interesting to go the other way as well:

**generated image → infer simple rules → p5.js reconstruction → change the code → model transformation**

For example, generate an image containing two circles, then write a small program that could produce a similar arrangement. It is not about recovering hidden code. It is about making a structure explicit and editable again.

That connects back to Session 1 and gives code a useful role after working with the model.

Mark Webster's neural drawings and print process can become a central reference there: a model as one stage inside a process that has decisions before and after it.

## Sources worth keeping open during class

- [Anna Ridler - Myriad (Tulips)](https://annaridler.com/myriad-tulips)
- [Anna Ridler - Mosaic Virus](https://annaridler.com/mosaic-virus)
- [Sofia Crespo - Neural Zoo](https://sofiacrespo.com/neural-zoo/)
- [Memo Akten - Learning to See](https://memo.tv/projects/2017/learning-to-see/)
- [Replicate - FLUX.2 Klein 4B](https://replicate.com/black-forest-labs/flux-2-klein-4b)
- [Replicate - FLUX 3 Image](https://replicate.com/black-forest-labs/flux-3-image)
- [Replicate - prediction data retention](https://replicate.com/docs/topics/predictions/data-retention/)

The detailed discussion prompts and links are also in `examples.md`.
