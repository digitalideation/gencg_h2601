# Session 5: Parameter Spaces
> We are not designing one result. We are designing a family of possible results.

In Session 4 we gave systems behaviours. Today we identify the values that shape those behaviours and explore what else the same system can produce. You can continue an existing sketch or begin a small generator. Faces are one possible direction, not the only one.  
**existing system → parameters → ranges and relationships → combinations → comparison → selection**

## 🟡 COLLABORATE
Define the idea, identify your parameters and make a meaningful first version before asking AI to help. AI can then help you understand code, refactor a function, add controls or question a relationship. It should not decide what your system is about or replace your first attempt.

Before collaborating, be able to explain: **What can change, what stays fixed, and why?** Keep your own process notes and record any meaningful AI contribution briefly.

## What we will explore
By the end of the session, you should be able to:
- identify a few meaningful parameters and define their ranges
- distinguish continuous values, discrete choices and linked parameters
- describe a small system in a reusable function
- compare combinations systematically rather than change values at random
- save configurations and explain why you selected them

→ [Examples and references](./examples.md)

## 1. Reopen a system
Choose a sketch from repetition, time or behaviour that you would like to explore further. Run it and identify three values that noticeably affect the result. A drawing machine might have a speed limit, turning range and trail length. A composition might have spacing, element size and number of elements.

Keep a copy of the working version. Explain one relationship to a partner: **changing this value changes this part of the system**. This is a short checkpoint, not a requirement to finish every earlier experiment.

## 2. Choose three meaningful parameters
Sketch the system on paper or in Excalidraw. Label the parts that can change and the relationships that should remain. For each parameter, write its name, its range or options, and what it controls.

For a simple face, this could be:
```text
head width: 80 to 160 pixels
eye spacing: 0.2 to 0.6 of the head width
eye shape: circle or rectangle
```

**Continuous:** a value varies along a range, such as width or spacing.  
**Discrete:** a choice comes from separate options, such as a shape type or a whole-number count.  
**Linked:** a value depends on another value, such as eye spacing relative to head width.

A parameter is a control you choose to expose. You do not need a slider for every variable in the program. Three useful controls are enough to begin.

## 3. Describe the system once
A function lets us describe a construction once and call it with different settings. This complete starter sketch draws three versions of a small radial module. You can use it to understand the method, then apply the method to your own system.

```js
function setup() {
  createCanvas(600, 200);
  angleMode(RADIANS);
  background(255);
  noLoop();

  drawModule(100, 100, 25, 6, 8);
  drawModule(300, 100, 45, 6, 8);
  drawModule(500, 100, 65, 6, 8);
}

function drawModule(cx, cy, radius, arms, dotSize) {
  push();
  stroke(0);
  fill(0);
  for (let i = 0; i < arms; i++) {
    const angle = TWO_PI * i / arms;
    const x = cx + cos(angle) * radius;
    const y = cy + sin(angle) * radius;
    line(cx, cy, x, y);
    circle(x, y, dotSize);
  }
  pop();
}
```

Here `cx` and `cy` place each version on the canvas. The design controls are `radius`, `arms` and `dotSize`. In this first comparison, only `radius` changes. Use a positive whole number for `arms`.

For your own sketch, identify a small part that can become a function. Avoid copying the whole program each time you want another variation.

## 4. Make a map of the possibilities
Choose two parameters and compare them in a **3 × 3 grid**. Change one from left to right and the other from top to bottom. Keep the third parameter fixed and label the values.

To try this with the starter above, keep `drawModule()` and replace only `setup()` with:

```js
function setup() {
  createCanvas(600, 600);
  angleMode(RADIANS);
  background(255);
  noLoop();
  textSize(12);
  textAlign(CENTER);

  for (let row = 0; row < 3; row++) {
    for (let column = 0; column < 3; column++) {
      const radius = 25 + column * 20;
      const arms = 3 + row * 3;
      const cx = 100 + column * 200;
      const cy = 100 + row * 200;
      drawModule(cx, cy, radius, arms, 8);
      noStroke();
      fill(0);
      text('radius ' + radius + ', arms ' + arms, cx, cy + 85);
    }
  }
}
```

This is not the whole parameter space. It is a small view of two parameters while the others stay fixed. The grid is now a comparison tool, not just a visual pattern.

For a moving system, a contact sheet of separate runs is fine. Reset the system and compare each run after the same elapsed duration. You do not need nine simulations running together.

## 5. Test the edges
Try the minimum and maximum settings, then test combinations near the limits. Does a small adjustment make a large difference? Do shapes overlap? Does a behaviour stop? Is that a mistake, or a possibility worth keeping?

Decide whether parameters should be independent. For example:
```js
const eyeSpacing = headWidth * spacingRatio;
```

Here spacing changes with the head rather than staying fixed in pixels. That relationship is a design decision. A strange result is not automatically wrong, but you should be able to explain whether you intended to allow it.

## 6. Add controls only where useful
Editing named values in the code is enough for the exercise. A slider can make a range easier to explore, but a large interface is not the goal.

To test one slider with `drawModule()`, replace the previous `setup()`, add the variable and `draw()` below, and keep the module function unchanged:

```js
let radiusControl;

function setup() {
  createCanvas(400, 400);
  angleMode(RADIANS);
  radiusControl = createSlider(20, 65, 45, 1);
  radiusControl.attribute('aria-label', 'Module radius');
}

function draw() {
  background(255);
  drawModule(200, 200, radiusControl.value(), 6, 8);
}
```

The slider defines a minimum, maximum, starting value and step. See the [p5.js `createSlider()` reference](https://p5js.org/reference/p5/createSlider/). A labelled choice is usually clearer than a continuous slider for a category such as circle or rectangle.

## 7. Question one relationship
After your first version and comparison grid, ask AI or a partner to review one relationship. For example:

> Here are my parameters and ranges. Identify one relationship I may have overlooked. Explain it without replacing my visual idea or rewriting the whole program.

Choose one suggestion to test. Keep the original and compare them under the same conditions. Did the change improve control, remove an interesting possibility, or misunderstand your intention? You can reject the suggestion. Collaboration does not require accepting everything offered.

## 8. Select a family
Choose **three contrasting configurations** from the same system. Save the values with each output so you can return to them. Give each configuration a short name and explain why it belongs in the family.

If randomness is involved, optionally use [p5.js `randomSeed()`](https://p5js.org/reference/p5/randomSeed/) at the start of each comparable run. The same seed repeats a random sequence, but changing the order or number of random calls changes how that sequence is used. Save the code version, inputs and run duration as well when they affect the result.

## Faces as one direction
A face generator makes relationships between parts easy to discuss, but you can also explore letters, plants, abstract forms, patterns or a drawing machine. Choose a system you can explain and keep its scope small.

→ [Faces and parametric generators](./faces.md)

## What to keep for your journal
Keep one connected record rather than a separate essay for each step:
- the starting sketch and a diagram of three parameters, their ranges and relationships
- a labelled 3 × 3 comparison, or equivalent captures from a moving system
- one limit or unexpected combination you investigated
- three selected configurations with their values and a short reason for choosing them
- a brief before/after note if AI or peer feedback changed the system

The main question is: **What makes these different outcomes belong to the same system?**

## Next session
In Session 6 we work with **Images as Data**. Here we chose values ourselves. Next we will explore how colour, brightness and other information from an image can become inputs to a system.

→ [Examples and references](./examples.md)  
→ [Faces and parametric generators](./faces.md)  
→ [Notes on this session](./teacher-notes.md)
