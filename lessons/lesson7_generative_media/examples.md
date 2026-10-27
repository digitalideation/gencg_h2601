# Session 7: Examples & References
## Generative Media

In the first six sessions, we built systems whose rules we could inspect and change directly. A learned image model works differently. Its output depends on training and model design as well as the inputs we choose.

These references are not a catalogue of image-generation styles. They ask different questions about **training material, interpretation, plausible images and creative decisions**.

While browsing, ask:

- What material or process existed before the model?
- What did the artist decide?
- What was learned from data, and what is specified at generation time?
- Which part of the output is difficult to predict?
- What happens after generation?

## Anna Ridler: Myriad (Tulips) and Mosaic Virus

<img src="https://images.squarespace-cdn.com/content/v1/5500326fe4b0564d4c2494d1/1668431003454-AHT75S8GQ6CDK5JKCL2R/low_38%2BKasseler%2BDokfest_Monitoring_%C2%A9Nicolas%2BWefers_JPEG-Qualita%CC%88t%2B100_%2B2.png" alt="Anna Ridler's Myriad (Tulips), a grid of photographed and annotated tulips" style="width:100%;height:auto;">

_[Anna Ridler, Myriad (Tulips), 2018](https://annaridler.com/myriad-tulips)._

Ridler photographed and hand-labelled thousands of tulips for `Myriad (Tulips)`. That collection became the training material for `Mosaic Virus`, in which generative images of tulips change over time.

The important point is that the artistic choices do not begin when a model produces an image. They also happen when someone decides **what belongs in the dataset**, which labels to use and what the resulting system should express.

In our session, we will use a pretrained model rather than assemble and train our own dataset. Ridler offers a different approach and makes the normally hidden preparation visible.

### Look for

- variation within a recognisable family
- human selection and annotation as creative work
- the difference between photographs, training data and generated images
- the relation between source material and the meaning of the work

### Questions

What does the model inherit from the tulip photographs? Which decisions were made long before generating an image? What would change if a different kind of flower, or a different way of labelling, had been used?

### References

- [Anna Ridler - Myriad (Tulips)](https://annaridler.com/myriad-tulips)
- [Anna Ridler - Mosaic Virus](https://annaridler.com/mosaic-virus)
- [Digital Art Museum - Myriad (Tulips)](https://dam.org/museum/artists_ui/artists/ridler-anna/myriad/)

## Sofia Crespo: Neural Zoo

_[Sofia Crespo, Neural Zoo, 2018-2022](https://sofiacrespo.com/neural-zoo/)._

`Neural Zoo` presents forms that look biologically plausible but do not belong to any familiar species. We recognise textures, organs or surface details while being unsure what kind of creature we are looking at.

This is useful when discussing how a model can produce something visually convincing without accurately describing an existing thing.

In Session 7, a model might turn a simple abstract drawing into something that looks like a photograph or a material object. That transformation can also introduce assumptions that were not present in the original.

### Look for

- familiar details recombined in unfamiliar ways
- consistency of texture despite unusual structure
- the tension between visual plausibility and factual truth
- differences between a new interpretation and a faithful translation

### Questions

Why do these images seem familiar? Which parts feel believable, and which do not? What does a model add when it tries to make an abstract composition look like something from the physical world?

### References

- [Sofia Crespo - Neural Zoo](https://sofiacrespo.com/neural-zoo/)
- [Sofia Crespo - artist's website](https://sofiacrespo.com/)

## Memo Akten: Learning to See

_[Memo Akten, Learning to See: Interactive, 2017](https://memo.tv/projects/2017/learning-to-see-interactive/)._

In `Learning to See`, custom neural networks reinterpret everyday objects captured by a camera as landscapes, flowers and other scenes. In the interactive version, someone can rearrange physical objects and see how their image is reconstructed through different learned visual worlds.

The work helps us discuss a model as an **interpretation system**, rather than a transparent filter that simply changes pixels.

This is not the same setup as the Replicate editing model we will use. Akten's work uses custom models and live input. The relationship is conceptual: what does the model bring to an image that we did not explicitly draw?

### Look for

- the source image and its interpreted output shown together
- the influence of changing the input arrangement
- different interpretations of similar objects
- the model's learned expectations becoming visible

### Questions

What information is preserved? What has been invented? Does the result tell us more about the objects on the table, or about what the model has learned?

### References

- [Memo Akten - Learning to See](https://memo.tv/projects/2017/learning-to-see/)
- [Memo Akten - Learning to See: Interactive](https://memo.tv/projects/2017/learning-to-see-interactive/)
- [Memo Akten - open-source demonstration](https://github.com/memo/webcam-pix2pix-tensorflow)

## Generating, editing and training are not the same thing

These artists help us separate several different ways of working with learned models.

**Training:** creating or adapting the model using examples. The choice and preparation of the dataset matter.  
**Text-to-image:** generating an image from a written description without a supplied source image.  
**Image editing or image conditioning:** providing an existing image as another input and asking the model to transform or reinterpret it.  
**Selection:** comparing results and deciding what to keep, reject or change next.

We will focus on **image editing using pretrained models**. We are not training a model in this session.

An instruction such as "keep the spacing" is not an exact geometrical constraint unless the model or workflow provides a way to enforce it. Observe what happens instead of assuming it will obey.

## Replicate: compare models, not just images

For the main investigation, use [FLUX.2 Klein 4B](https://replicate.com/black-forest-labs/flux-2-klein-4b), an Apache-2.0 licensed model supporting image editing.

For a second comparison, try [FLUX 3 Image](https://replicate.com/black-forest-labs/flux-3-image). It is a different model with a different set of controls, not simply a more expensive setting of Klein. Its `Grounding` option should be turned off for a comparison that relies only on your supplied inputs.

The interface can change. Before a class, check model availability, supported file formats, pricing and account access.

### Look for

- the prompt and input-image fields
- aspect ratio and output resolution
- optional seed controls (not every model has them)
- model-specific settings that make comparisons less direct

### Try this

Use the same simple image in both models. Ask for three distinct material transformations, one at a time.

Keep the input image fixed and save the settings alongside the outputs. Ask:

> Which differences follow my instruction, and which seem characteristic of the model?

A six-image sheet is a **qualitative comparison**, not proof that one model is universally more creative or accurate.

### References

- [Replicate - FLUX.2 Klein 4B](https://replicate.com/black-forest-labs/flux-2-klein-4b)
- [Replicate - FLUX 3 Image](https://replicate.com/black-forest-labs/flux-3-image)
- [Replicate - running models](https://replicate.com/docs/topics/models/run-a-model)
- [Replicate - data retention](https://replicate.com/docs/topics/predictions/data-retention/)

## Things to investigate

When comparing generated and edited images, ask:

1. What did the original image contribute?
2. Which instruction did the model follow?
3. What did it ignore or reinterpret?
4. Which new details were not present in the source?
5. What assumptions about material, lighting or space appear?
6. What changes when the same image goes through a different model?
7. How much variation appears with identical inputs?
8. Which result best serves the idea, rather than simply looking polished?
9. What would be lost if we removed the model?
10. What could we do with the image next?

The goal is not to collect as many generated images as possible. It is to **learn what this material does and decide how to work with it**.

→ [Notes on this session](./teacher-notes.md)  
→ [Back to Session 7](./README.md)
