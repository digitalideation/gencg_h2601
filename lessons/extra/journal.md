# The Process Journal

## What is the journal?

The journal is a living record of your technical experiments, artistic thinking and changing decisions throughout the semester. It is not a portfolio of finished work and it is not meant to be a polished weekly essay.

The journal is inspired by **Vera Molnár's practice** of developing algorithmic ideas through writing and drawing. Before she had access to computers, Molnár imagined procedures by hand using what she called her *machine imaginaire*—an imaginary machine.

Explore examples from her notebooks:

- [Vera Molnár journal, part 1](../../assets/pdf/vera_journal_01.pdf)
- [Vera Molnár journal, part 2](../../assets/pdf/vera_journal_02.pdf)

Your own journal can combine Markdown notes, code, screenshots, diagrams, scanned drawings, references, questions and unfinished experiments.

## Why keep a journal?

Consistent documentation helps you:

- articulate algorithmic thinking in words, sketches and code
- understand creative work as an iterative process
- record successes, failures and unexpected results
- build a personal visual and technical vocabulary
- reflect critically on your creative decisions
- see connections between experiments across the semester
- explain how and why a project developed

Document while you work. A short observation captured at the right moment is often more useful than a long reconstruction written weeks later.

## What to document each week

Each weekly entry should include four connected elements. They do not need to have equal length, but all four should be visible in your documentation.

### 1. Exploration and experimentation

Show what you tried:

- code experiments, including incomplete or failed attempts
- visual sketches and Excalidraw diagrams
- parameters, values and ranges you tested
- variations of the same system
- technical problems and how you approached them
- screenshots or recordings of meaningful states

Do not include only the final version. Show enough intermediate material to make the development of the work understandable.

### 2. Influences and references

Connect your work to a wider context:

- artists and artworks
- readings, examples and technical resources
- visual or conceptual references
- links, images and citations
- a short explanation of why each reference matters

A list of links is not enough by itself. Describe what you noticed and how it influenced your experiment or decision.

### 3. Algorithmic thinking

Make the system behind the work visible:

- rules, relationships and conditions
- what remains fixed and what can vary
- parameters and constraints
- how code produces visual or behavioural outcomes
- pseudocode, flow diagrams or annotated sketches
- changes you made to the system and their effects

Try to describe the logic in plain language as well as showing the code.

### 4. Critical reflection

Reflect on the process:

- What worked?
- What failed or remained unresolved?
- What surprised you?
- Why did you make particular visual or technical choices?
- Which ambiguity or unexpected behaviour was useful?
- What would you change?
- What questions emerged?
- What will you explore next?

Be specific. Instead of writing “I changed the colours,” explain what you changed, why you changed it and what effect it had.

## Working format

Create your own repository from the **[Generative Computer Graphics Journal template](https://github.com/digitalideation/gencg_h2601_journal)**. The template contains the current technical instructions for:

- creating and cloning your repository
- opening it as an Obsidian vault
- installing the recommended plugins
- organizing weekly entries and sketches
- embedding images, Excalidraw drawings and p5.js sketches
- using Git and GitHub
- publishing the journal with Quartz and GitHub Pages

Follow the template's README as the authoritative setup guide.

Your work will normally be organized by week:

```text
weeks/
├── w01/
│   ├── index.md
│   ├── journal.md
│   └── sketches/
├── w02/
│   └── ...
attachments/
Excalidraw/
index.md
```

Use relative paths for local media and code. Keep filenames clear, organize material as you add it, and check the published journal after pushing changes.

Because the journal repository is public, never commit passwords, API keys, personal information or material that should remain private.

## A useful weekly entry structure

You may adapt this structure to suit your process:

```markdown
# Week 03 — Grid Systems and Variation

## Exploration

I began with a regular grid of circles, then tested several spacing values
and introduced variation with a modulo operation.

[Include code, screenshots and sketches.]

## References

Vera Molnár's use of small disruptions within ordered systems made me think
about how little variation is needed before a pattern feels unstable.

[Include links and properly credited images.]

## Algorithmic thinking

My system:

- Create an N × N grid.
- Calculate each cell's distance from the centre.
- Change the shape when a cell meets a defined condition.
- Keep colour and spacing fixed for this test.

[Include pseudocode or a diagram.]

## Reflection

The most random version was less interesting because the underlying rule
became difficult to perceive. Next I will keep the positions regular and
vary only size.

Questions:

- How much disruption can the grid hold before it stops reading as a grid?
- Would animation clarify or hide the rule?
```

This is an example, not a mandatory writing template. Use headings and formats that make your own process easy to follow.

## Common pitfalls

### Posting code without explaining it

The journal is not only a code repository. Explain what the code was meant to do, what changed and what you learned from it.

### Documenting only successful outcomes

Failed experiments are useful evidence. Include them when they reveal something about the system or influence your next decision.

### Omitting visual thinking

Use drawings, diagrams, screenshots and variations. Visual evidence is essential in a creative coding journal.

### Writing vague reflections

Statements such as “it looks cool” do not explain a decision. Identify the qualities you noticed and the rules or parameters that produced them.

### Collecting references without making connections

Credit your sources and describe how they relate to your own questions or experiments.

## Assessment

The process journal contributes **40% of the final grade**. It is considered through the following qualities:

- **Consistency and regularity:** sustained weekly documentation without large gaps
- **Depth of documentation:** meaningful technical and artistic evidence, including sketches and code
- **Quality of reflection:** critical analysis, learning, iteration and clearly explained decisions
- **Use of references:** relevant, credited sources connected thoughtfully to your own work

The journal should demonstrate development over time. Evaluation focuses on the quality and visibility of your process rather than polished writing or consistently successful outcomes.

## Milestones across the 12 sessions

### Session 1

- Create your journal repository from the template.
- Complete the setup and publishing steps.
- Make your first entry with evidence from the instruction and rule-system exercises.

### Sessions 2–4

- Establish a regular documentation rhythm.
- Build your visual and technical vocabulary.
- Record experiments, variations and questions as they happen.

### Sessions 5–8

- Review earlier entries and identify recurring interests.
- Use feedback to improve the clarity and depth of your documentation.
- Connect techniques and ideas across sessions.

### Sessions 9–11

- Document the concept, prototypes, tests and revisions for your final project.
- Show how feedback and failed attempts affect the system.
- Prepare the journal to communicate the full development process.

### Session 12

- Complete a final reflection on the semester.
- Check that embedded media, code and external links remain accessible.
- Make sure the journal clearly shows the path from early experiments to the final project.

## Start here

1. Open the [journal template](https://github.com/digitalideation/gencg_h2601_journal).
2. Create your own repository using **Use this template**—do not fork it.
3. Follow the setup and publishing instructions in its README.
4. Open the cloned repository in Obsidian and VS Code.
5. Begin documenting Session 1.

Remember: the journal is first a tool for learning, noticing and developing your practice. Its value comes from using it continuously.
