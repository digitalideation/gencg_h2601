# Getting Started: Course Setup

Before the first session, prepare the basic tools we will use during the semester.
You do not need to understand everything yet. The goal is simply to have the software installed and your accounts ready.

- [1. GitHub account](#1-github-account)
- [2. Install Git](#2-install-git)
- [3. Install VS Code](#3-install-vs-code)
  - [Recommended extension](#recommended-extension)
- [4. Install Obsidian](#4-install-obsidian)
- [5. Install Excalidraw in Obsidian](#5-install-excalidraw-in-obsidian)
- [6. Test p5.js locally](#6-test-p5js-locally)
- [7. Browser](#7-browser)
- [Before the first session](#before-the-first-session)
- [What you do not need yet](#what-you-do-not-need-yet)

## 1. GitHub account

You will use GitHub to keep a versioned copy of your work throughout the semester.
If you do not already have an account:

- create one at [github.com](https://github.com/)
- make sure you can sign in
- verify your email address

We will use Git for a simple workflow:
**edit → test → commit → push**

You do not need to learn Git commands before the course.

## 2. Install Git

Git keeps track of changes to your files and connects your local project to GitHub.
Download and install: [Git](https://git-scm.com/)  
If VS Code is already open during installation, restart it afterwards.

## 3. Install VS Code

We will use Visual Studio Code as our main coding environment.
Download: [Visual Studio Code](https://code.visualstudio.com/)

VS Code will be used for:

- JavaScript
- p5.js sketches
- HTML and CSS
- testing projects locally
- Git commits
- pushing work to GitHub
- later API and generative media experiments

### Recommended extension

Install this extension from the VS Code Extensions panel:

**p5.js 2.x Project Generator**
This extension adds useful p5.js support to VS Code, including:

- p5.js autocomplete
- function and parameter hints
- hover documentation
- links to the p5.js reference
- p5.js project creation
- local preview with Live Server

[p5.js 2.x Project Generator](https://marketplace.visualstudio.com/items?itemName=Irti.p5js-project-generator)

VS Code already includes JavaScript autocomplete, so you do not need to install a separate JavaScript extension.

If you already use other VS Code extensions, you can keep them.  
If you use an AI coding assistant such as GitHub Copilot, make sure you know how to disable it when an exercise is marked **🔴 HUMAN**.

## 4. Install Obsidian

We will use Obsidian for the process journal.  
Download: [Obsidian](https://obsidian.md/)

The journal will contain things such as:

- notes
- sketches
- screenshots
- references
- experiments
- questions
- failed attempts
- short reflections
- documentation of your process

The exact journal structure will be introduced separately.

## 5. Install Excalidraw in Obsidian

We will use Excalidraw for quick visual thinking.
Inside Obsidian:

1. Open **Settings**
2. Go to **Community plugins**
3. Enable community plugins if necessary
4. Search for **Excalidraw**
5. Install and enable it

Plugin: [Obsidian Excalidraw](https://github.com/zsviczian/obsidian-excalidraw-plugin)

You do not need to learn Excalidraw before class. We will use it for:

- system diagrams
- arrows and relationships
- layouts
- algorithm sketches
- parameter diagrams
- visual notes
- quick ideas

The drawings do not need to be polished.

## 6. Test p5.js locally

A basic p5.js project usually contains an `index.html` file and a `sketch.js` file.
Your `sketch.js` might look like this:

```js id="vr3hnh"
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(240);
  circle(200, 200, 100);
}
```

To run it locally:

1. open the project folder in VS Code
2. open `index.html`
3. start the local server from VS Code
4. your browser should open the sketch
5. edit `sketch.js`
6. save and check the result in the browser

Do not worry if the code itself is unfamiliar. We will work through it together.

## 7. Browser

Use a modern browser such as:

- Chrome
- Firefox
- Edge
- Safari

For development, Chrome or Firefox can be useful because their developer tools make JavaScript errors easy to inspect.

## Before the first session

Please arrive with:

- [ ] GitHub account ready
- [ ] Git installed
- [ ] VS Code installed
- [ ] p5.js 2.x Project Generator installed
- [ ] Obsidian installed
- [ ] Excalidraw plugin installed
- [ ] a modern browser available

If something does not work, do not spend hours trying to fix it alone. Bring the problem to class and we will troubleshoot it.

## What you do not need yet

You do **not** need to install or configure:

- Node.js
- npm
- Vite
- Three.js
- TouchDesigner
- Replicate
- AI APIs
- additional JavaScript frameworks

We will introduce additional tools only when they become useful.
