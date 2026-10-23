# Session 6: Images as Data
> An image can be more than a picture to display. It can supply the values for another system.

In Session 5 we chose parameters and explored their combinations. Today some of those values come from an image. We will read colours, sample positions and decide how that information becomes a new visual result.  
**choose an image → sample → read values → define a mapping → transform → compare**

## 🟡 COLLABORATE
Describe your mapping and make a first attempt before asking AI to help. AI can explain image loading, investigate an error or help improve an implementation. It should not replace your visual idea with an unrelated effect.

Keep the source image and your first version. If AI suggests a change, test whether it still follows the rule you intended. Write your own observations and briefly record any meaningful contribution.

## What we will explore
By the end of the session, you should be able to:
- load an image and read colour values at selected positions
- distinguish the source image, the sampling strategy and the drawing rule
- use image values to control shapes or a system you have already made
- compare a transformation using different settings and different source images
- export a result and explain what the process preserves or changes

→ [Examples and references](./examples.md)

## 1. Choose the material
Choose a photograph, texture, drawing or exported p5.js sketch. Start with a small, opaque JPEG or PNG. Use an image you made or have permission to work with, and keep its source credit.

Look at it before writing code. Are the important differences in colour, light and dark, texture or arrangement? Sketch one relationship on paper or in Excalidraw:
```text
dark areas → larger black marks
sample colour → colour of a drawing module
sample position → position in a different arrangement
```

Choose one relationship first. The source should matter to the idea, not just be the first photograph you find.

## 2. Load and inspect the image
In your local p5.js project, put your chosen image next to `index.html` and name it `source.jpg`. Use the actual extension if it is a PNG. Open the project through Live Server, not by double-clicking the HTML file.

This starter uses **p5.js 2.x**, as in the course setup. `await` lets the image finish loading before the following lines use it. Keep only one `setup()` function in the sketch.

```js
let img;
const sampleStep = 12;

async function setup() {
  createCanvas(640, 480);
  pixelDensity(1);
  colorMode(RGB, 255);
  noLoop();

  try {
    img = await loadImage('source.jpg');
  } catch (error) {
    background(255);
    fill(0);
    text('Could not load source.jpg. Check the file and local server.', 20, 40);
    console.error(error);
    return;
  }

  // Fit a working copy inside 640 x 480 without stretching it.
  const scaleFactor = min(640 / img.width, 480 / img.height, 1);
  img.resize(
    max(1, floor(img.width * scaleFactor)),
    max(1, floor(img.height * scaleFactor))
  );
  resizeCanvas(img.width, img.height);
  image(img, 0, 0);

  const c = img.get(floor(img.width / 2), floor(img.height / 2));
  console.log('Centre sample [red, green, blue, alpha]:', c);
}
```

`img.get(x, y)` reads the image, rather than whatever has already been drawn on the canvas. It returns four values: **red, green, blue and alpha**. For these samples, the channels run from 0 to 255; alpha describes opacity. See the [image-loading reference](https://p5js.org/reference/p5/loadImage/) and [image-sampling reference](https://p5js.org/reference/p5.Image/get/).

The working copy is resized in memory. Your original file stays unchanged. We keep image and canvas dimensions equal here so their coordinates line up.

## 3. Rebuild it from samples
Keep the starter above. Replace `image(img, 0, 0);` with `drawSamples();`, then add this function below `setup()`:

```js
function drawSamples() {
  background(255);
  noStroke();

  for (let y = 0; y < img.height; y += sampleStep) {
    for (let x = 0; x < img.width; x += sampleStep) {
      const cellWidth = min(sampleStep, img.width - x);
      const cellHeight = min(sampleStep, img.height - y);
      const c = img.get(x, y);

      fill(c[0], c[1], c[2]);
      rect(x, y, cellWidth, cellHeight);
    }
  }
}
```

Each rectangle uses one sampled colour, not the average colour of its whole area. The last row and column are clipped to the image dimensions.

Change `sampleStep` to 6, 12 and 24, reloading the page each time. Keep it a positive whole number. Compare the reconstructions before changing the drawing rule.

> **How much can you leave out while the image is still recognisable?**

This is your baseline. Keep one capture alongside the original.

## 4. Change what the values control
Now keep the sampling positions and replace the two drawing lines inside the inner loop, `fill(...)` and `rect(...)`, with:

```js
const tone = (c[0] + c[1] + c[2]) / 3;
const diameter = map(tone, 0, 255, min(cellWidth, cellHeight), 0);
fill(0);
circle(x + cellWidth / 2, y + cellHeight / 2, diameter);
```

This simple channel average gives us a light-dark estimate. It is not a precise measure of perceived brightness. On the white canvas, darker samples produce larger black circles and lighter samples produce smaller ones.

Reverse the mapping by swapping the last two arguments of `map()`. Predict the result before running it. Then try changing the mark rather than the sample: a short line, a symbol or a module from Session 5.

**sample → value → mapping → mark** is the relationship to keep visible. Reading these values does not mean that the program recognises a face, a tree or any other subject in the image.

## 5. Develop one transformation
Choose one direction and develop it gradually. You could replace samples with custom marks, rearrange small image fragments, reduce the available colours, or use sampled values to guide a drawing process.

A module from Session 5 can receive its size from an image instead of a manually chosen number. A drawing machine from Session 4 could read a sample near its current position and use it to change direction or mark size.

Keep the first version small enough to explain. Pixel sorting, comparisons between neighbours, 3D, webcam input, video and sound are possible extensions, not a checklist for today.

For larger operations, direct access through `img.pixels` can be more efficient than repeated `get()` calls. There is a short [pixel-array extension on the examples page](./examples.md#going-further-read-the-pixel-array). It can wait until your mapping works.

## 6. Compare the rule and the source separately
Make two variations of your transformation using the same image. Change one setting or drawing relationship at a time and label what changed.

Then apply one unchanged configuration to a second image. Keep the sampling step, mapping and other settings fixed. For a close comparison, prepare both working images at the same dimensions. Otherwise record the dimension difference too.

Ask: **What comes from my rule, and what comes from the image?** Does the second source reveal something the first one hid? Does the transformation preserve colour but lose spatial relationships? Does it only work well with a particular kind of source?

The aim is one system tested deliberately, not several unrelated filters.

## 7. Review one implementation decision
Once the mapping has been attempted, ask AI or a partner to inspect the code against that intention. For example:

> Darker samples should produce larger marks. Here is my implementation and what I observe. Does it follow that rule? Explain any mismatch and suggest the smallest change, without replacing the transformation.

Test a suggestion with simple black, grey and white samples before returning to the full image. An attractive result is not enough to prove that the intended rule is working. Keep or reject the suggestion based on that comparison.

You do not need to upload the photograph to get help with indexing or a numerical mapping. Code and a few example values are often enough.

## 8. Export a result
Keep a result that could become the input to another process. Add this function to save the canvas when you press `S`:

```js
function keyPressed() {
  if (img && (key === 's' || key === 'S')) {
    saveCanvas('image-study-step-' + sampleStep, 'png');
  }
}
```

Keep the original image, the exported result and the settings together. Rename outputs clearly when comparing different mappings. [p5.js `saveCanvas()`](https://p5js.org/reference/p5/saveCanvas/) exports the canvas, not the source file.

## What to keep for your journal
Keep one connected record of the experiment:
- both source images, with their credits or a note that they are your own
- the mapping sketch and one coarse reconstruction
- two variations using the first source, with the changed setting identified
- one of those configurations applied to the second source
- the exported result, code and a short note about any AI or peer contribution

A few observations are enough: what survived, what disappeared, what surprised you, and why the source was worth transforming.

## Next session
In Session 7 we move into **Generative Media**. Here we specified the transformations ourselves. Next we will explore what changes when a learned model becomes part of the process. An exported image from this session can become one possible input, but there is no need to generate an AI image yet.

→ [AI and Creativity](../extra/ai-and-creativity.md): a short annex with questions about learning, agency and collaboration as AI becomes part of the work.

→ [Examples and references](./examples.md)  
→ [Notes on this session](./teacher-notes.md)
