# Session 8: Examples & References
## Hybrid Pipelines

An image can be the output of one system and the input to another. These artists work across **generative code, learned models and other media**, but they do so in different ways.

Look at **what each stage contributes**, not only the finished image. None of these examples needs to be copied technically for our workshop.

## Mark Webster: Neural Drawings

_[Mark Webster, Neural Drawings](https://verse.works/journal/on-neural-drawings-of-mark-webster)._

Webster combines imagery made with generative algorithms, a neural-network transformation and physical printmaking. The algorithm provides a structure, the network reinterprets it, and the printing process introduces another set of material choices.

This is a useful example of a pipeline with decisions **before and after** the AI stage. It is not necessarily made with p5.js.

### Look for

- what survives from the algorithmic drawing
- what changes during neural reinterpretation
- what a physical print contributes beyond a digital output

### Questions

Why not stop at the code-generated drawing? Why not use the model alone? What does the printmaking stage add?

### References

- [On the Neural Drawings of Mark Webster (interview and process)](https://verse.works/journal/on-neural-drawings-of-mark-webster)
- [Mark Webster's development work](https://mwebster.online/dev/page-3)

## JCode: What Remains (2026)

_[JCode, What Remains](https://www.jcode.art/)._

The artist describes a workflow in which photographic material is transformed through **p5.js code** and then reinterpreted by a custom image model (a LoRA-based process). This is the closest example to the **code → AI image** part of our workshop.

The original work addresses conflict and its representation. We are studying the structure of the process, not asking you to use the same subject matter.

### Look for

- how the coded stage changes the source before it reaches the model
- which decisions are explicit in the p5.js system
- how the learned model changes what the image appears to depict

### Questions

Why introduce code between a source image and a model? How would the result differ if the model interpreted the original photograph directly?

### Reference

- [JCode: works and project information](https://www.jcode.art/)

## Botto: Algorithmic Evolution (2024–2025)

_[Botto, Algorithmic Evolution](https://verse.works/series/algorithmic-evolution-by-botto)._

Botto's project expanded from image-generation systems into **p5.js-based generative code**. AI proposes and revises code, with evaluation and selection shaping the results. Botto's documentation also describes links between those algorithms and later image-to-image processes.

This differs from our exercise: we are not building an autonomous artist. It is a reference for treating **code as something that can be generated, inspected, edited and selected**, not just a way to export pixels.

### Look for

- a family of images produced by related rules
- what changes when the code changes
- the role of feedback and selection

### Questions

What becomes possible when the generated outcome is editable code rather than a fixed image? If an AI writes the code, what creative decisions remain?

### References

- [Algorithmic Evolution collection](https://verse.works/series/algorithmic-evolution-by-botto)
- [Botto's p5.js process documentation](https://docs.botto.com/collections/p5.botto)
- [Botto's p5.js Study: An Evolving Organism](https://verse.works/journal/bottos-p5js-study-an-evolving-organism)

## Optional: Surya Narreddi, Training AI to Paint with Code (2026)

This project trains a language model to produce JavaScript drawing instructions using **p5.brush**, rather than generating only a finished bitmap. The resulting code can be examined and modified.

We are **not** training models in this workshop. The interesting idea is that AI may produce editable instructions rather than final pixels.

- [Training AI to Paint with Code](https://surya.website/rling-qwen-to-paint-with-code)

## Some creative directions

Choose one direction that interests you. These are possibilities, not separate assignments.

| Starting image | Rule to reconstruct in p5.js | Meaningful coded change | Model reinterpretation |
| --- | --- | --- | --- |
| **Invented ecosystem** | Clusters or branching | Change growth, density or variation | An imaginary organism |
| **Visual alphabet** | Repeated geometric symbols | Invent combinations or a symbol grammar | Signs, inscriptions or objects |
| **Imaginary city** | Blocks and street spacing | Change density or connectivity | A fictional landscape |
| **Abstract rhythm** | Repetition, scale and alignment | Add pulses, shifts or controlled irregularity | A physical material or environment |

Try to make each stage necessary. A different visual style is less interesting than a genuine change in **what the system can do**.

→ [Back to Session 8](./README.md)  
→ [Teacher notes](./teacher-notes.md)
