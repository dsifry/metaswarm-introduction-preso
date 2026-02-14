# metaswarm Introduction Presentation — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Build a polished Reveal.js presentation introducing metaswarm to entrepreneurs/founders, with 16 slides across 3 acts, custom dark theme with amber accent, and speaker notes.

**Architecture:** Single-page HTML app using Reveal.js 5.x via CDN. Custom CSS theme overrides. No build step — open index.html in a browser. All content self-contained.

**Tech Stack:** HTML5, CSS3, Reveal.js 5.2.1 (CDN), Inter font (Google Fonts)

---

### Task 1: Project scaffolding

**Files:**
- Create: `package.json`
- Create: `README.md`
- Create: `.gitignore`

**Step 1: Create package.json**

```json
{
  "name": "metaswarm-introduction-preso",
  "version": "1.0.0",
  "description": "Introduction presentation for metaswarm — Quality at Speed",
  "author": "Dave Sifry",
  "license": "MIT",
  "private": false,
  "repository": {
    "type": "git",
    "url": "https://github.com/dsifry/metaswarm-introduction-preso"
  }
}
```

**Step 2: Create .gitignore**

```
.DS_Store
node_modules/
*.swp
*~
```

**Step 3: Create README.md**

A short README explaining what this is, how to view it, and presenter controls.

**Step 4: Commit**

```bash
git add package.json .gitignore README.md
git commit -m "chore: project scaffolding"
```

---

### Task 2: Create custom CSS theme

**Files:**
- Create: `css/custom.css`

**Step 1: Create the custom theme**

Build a CSS file that overrides Reveal.js defaults with:
- Deep charcoal background (#1a1a2e)
- Inter font family for all text
- Amber/gold (#f0b429) accent color for highlights, links, emphasis
- Light text colors (#e0e0e0 body, #ffffff headings)
- Styled code blocks on slightly lighter panels (#252547)
- Subtle fragment animations (fade-in)
- Custom classes: `.accent` for amber text, `.stat-number` for large numbers, `.terminal-block` for fake terminal output, `.flow-diagram` for pipeline visuals
- Clean spacing: generous margins, no clutter
- Responsive font sizing

**Step 2: Verify**

Open index.html (created in next task) in browser and verify theme applies correctly.

**Step 3: Commit**

```bash
git add css/custom.css
git commit -m "feat: custom dark theme with amber accent"
```

---

### Task 3: Create index.html with Reveal.js and Act I slides (slides 1-4)

**Files:**
- Create: `index.html`

**Step 1: Create the HTML shell**

Set up index.html with:
- Reveal.js 5.2.1 CSS and JS from CDN (`cdn.jsdelivr.net/npm/reveal.js@5.2.1/`)
- Include `dist/reveal.css` (core), `dist/theme/black.css` (base theme), and our `css/custom.css` (overrides)
- Include Highlight.js plugin for code blocks (`plugin/highlight/highlight.js` and `plugin/highlight/monokai.css`)
- Include Notes plugin for speaker notes (`plugin/notes/notes.js`)
- Inter font from Google Fonts
- Reveal.initialize() with: hash: true, plugins, transition: 'fade', controlsTutorial: false

**Step 2: Add Act I slides**

**Slide 1 — Title:**
- "metaswarm" as large heading
- "Quality at Speed" as subtitle with `.accent` class
- "Dave Sifry" and date below
- Speaker notes: "Welcome everyone. I'm Dave Sifry. I want to show you something that's changed how I build software."

**Slide 2 — The Problem:**
- "Moving fast usually means cutting corners."
- Fragment reveal: "What if your tools enforced quality automatically?"
- Speaker notes: "As founders, we're always under pressure to ship. But every shortcut becomes tech debt. What if the tooling itself prevented cutting corners?"

**Slide 3 — GitHub Contribution Graph:**
- Placeholder for the GitHub contribution graph image (we'll capture this separately)
- Caption: "Built with metaswarm." in small, understated text
- Speaker notes: "This is my GitHub over the last month. I'm not going to read you the numbers — you can see for yourself. All of this was built using what I'm about to show you."

**Slide 4 — What is metaswarm?:**
- "An open-source orchestration framework that coordinates AI agents through a structured development workflow — from idea to merged PR."
- Fragment reveal of key concepts: "18 agents. 9 phases. Git-native knowledge base."
- Speaker notes: "metaswarm is open source. It gives Claude Code a structured workflow with specialized agents. Let me show you what that looks like."

**Step 3: Verify in browser**

Open index.html, confirm:
- Dark theme applies
- Slides navigate with arrow keys
- Fragments animate on click
- Speaker notes appear with 'S' key

**Step 4: Commit**

```bash
git add index.html
git commit -m "feat: Act I slides — title, problem, proof, definition"
```

---

### Task 4: Add Act II slides (slides 5-10)

**Files:**
- Modify: `index.html`
- Possibly modify: `css/custom.css` (for new visual elements)

**Step 1: Add Slide 5 — One Command**

- Heading: "One Command"
- Styled terminal block showing:
  ```
  $ npx metaswarm init

  ✓ Created CLAUDE.md
  ✓ Created .coverage-thresholds.json
  ✓ Scaffolded 18 agents
  ✓ Scaffolded 9 skills
  ✓ Scaffolded 7 commands
  ✓ Scaffolded 6 rubrics
  ✓ Scaffolded 6 guides
  ✓ Created knowledge base templates

  metaswarm is ready.
  ```
- Use fragment reveals for each line
- Speaker notes: "One command. That's it. Let me show you what it creates."

**Step 2: Add Slide 6 — What You Get**

- Visual tree/grid showing the 4 categories:
  - Agents (18) — Researcher, Architect, Coder, Reviewer, Security Auditor...
  - Skills (9) — Orchestrated Execution, Design Review Gate, PR Shepherd...
  - Commands (7) — start-task, review-design, pr-shepherd, prime...
  - Knowledge Base — patterns, gotchas, decisions, anti-patterns
- Use CSS grid layout with rounded cards for each category
- Speaker notes: "Agents are specialized roles. Skills are workflows. Commands are how you interact. The knowledge base is how it learns."

**Step 3: Add Slide 7 — The Workflow**

- 9-phase flow diagram built with CSS flexbox/grid:
  Research → Plan → Plan Review → Design Review → Decompose → Execute (TDD) → Final Review → PR → Shepherd
- Progressive reveal (each phase appears on click)
- Highlight the Execute phase as a loop (implement → validate → review → commit)
- Speaker notes: "Every task follows this pipeline. The key is that each phase has quality gates — the system won't let you skip steps."

**Step 4: Add Slide 8 — Trust Nothing, Verify Everything**

- Two-column comparison:
  - Left (red-tinted): "Agent says: 'All tests pass'" with ✗
  - Right (green-tinted): "Orchestrator runs tests independently" with ✓
- Key message: "The orchestrator never trusts self-reports. It verifies everything by running the tests itself."
- Speaker notes: "This is the core philosophy. It's like having a QA team that doesn't take the developer's word for it."

**Step 5: Add Slide 9 — It Learns**

- Visual showing knowledge entries accumulating:
  - "Pattern: Always mock external APIs in tests"
  - "Gotcha: This API returns 200 even on errors"
  - "Decision: Use repository pattern for data access"
- Caption: "Every PR teaches the system something new."
- Speaker notes: "The knowledge base is stored in git as JSONL. It grows organically. Agents prime from it before each task, so mistakes don't repeat."

**Step 6: Add Slide 10 — Getting Started**

- Simple transition slide: "Let's build something together."
- Subtitle: "Open your laptops."
- Speaker notes: "Okay, enough slides. Let's actually do this. Open your terminal."

**Step 7: Verify all slides in browser**

**Step 8: Commit**

```bash
git add index.html css/custom.css
git commit -m "feat: Act II slides — workflow, architecture, philosophy"
```

---

### Task 5: Add Act III slides (slides 11-16)

**Files:**
- Modify: `index.html`
- Possibly modify: `css/custom.css`

**Step 1: Add Slide 11 — Prerequisites**

- Checklist style:
  - ☐ Claude Code installed
  - ☐ Node.js 18+ (`node --version`)
  - ☐ GitHub CLI (`gh --version`)
  - ☐ A project (or we'll create one)
- Speaker notes: "Quick check — raise your hand if you have Claude Code installed. Great. Node.js? GitHub CLI? If you're missing anything, that's okay — pair up with someone who has it."

**Step 2: Add Slide 12 — The Friendliest Install**

- Show the conversational approach:
  - Terminal prompt showing Claude Code
  - User types: "Read through https://github.com/dsifry/metaswarm and install it for my project"
  - Claude responds by reading the repo and adapting the scaffold
- Caption: "Just tell Claude what you want."
- Speaker notes: "This is the key insight — you don't need to memorize commands. Just tell Claude Code to read the metaswarm repo and set it up. It will read the documentation, understand your project, and adapt the scaffold."

**Step 3: Add Slide 13 — What Claude Set Up**

- Show the resulting project structure in a terminal-style block
- Highlight key files: CLAUDE.md, agents/, skills/, knowledge/
- Speaker notes: "Claude read your project, understood its structure, and set up metaswarm tailored to it. Look at the CLAUDE.md — it's configured for your stack."

**Step 4: Add Slide 14 — Your First Task**

- Show creating an issue and starting work:
  - "Create a GitHub issue describing a small feature"
  - `/project:start-task <issue-number>`
- Speaker notes: "Pick something small. A new endpoint, a UI component, a bug fix. Create a GitHub issue for it. Then use the start-task command."

**Step 5: Add Slide 15 — Watch the Workflow**

- Animated flow showing the agents activating:
  - Researcher explores the codebase
  - Architect creates a plan
  - Reviewers validate the plan
  - Coder implements with TDD
  - PR gets created and shepherded
- Speaker notes: "Now watch. The researcher explores your codebase. The architect creates a plan. Reviewers validate it. The coder implements with tests. A PR gets created. And the shepherd monitors it to merge."

**Step 6: Add Slide 16 — Resources & Q&A**

- GitHub link: github.com/dsifry/metaswarm
- "Questions?" in large text
- Speaker notes: "The repo is open source. Star it, clone it, file issues. Happy to take questions now."

**Step 7: Verify all slides in browser**

**Step 8: Commit**

```bash
git add index.html css/custom.css
git commit -m "feat: Act III slides — hands-on workshop guide"
```

---

### Task 6: Capture GitHub contribution graph

**Files:**
- Create: `images/github-graph.png`

**Step 1: Capture the contribution graph**

Take a screenshot of the GitHub contribution graph from https://github.com/dsifry. Crop to just the contribution calendar. Save as `images/github-graph.png`.

Note: This may need to be done manually by Dave, or we can use the GitHub API to generate a contribution visualization.

**Step 2: Update slide 3 to reference the image**

Replace the placeholder with the actual image path.

**Step 3: Commit**

```bash
git add images/github-graph.png index.html
git commit -m "feat: add GitHub contribution graph to slide 3"
```

---

### Task 7: Polish and speaker notes review

**Files:**
- Modify: `index.html`
- Modify: `css/custom.css`

**Step 1: Review all speaker notes for flow**

Read through all speaker notes in sequence. Ensure they flow naturally as a talk — no jarring transitions, consistent tone (humble, practical, not sales-y).

**Step 2: Check all fragment animations**

Click through every slide. Verify fragments reveal in the right order and look clean.

**Step 3: Check responsive behavior**

Resize the browser window. Verify text doesn't overflow or break on smaller screens.

**Step 4: Final CSS polish**

Any spacing, color, or typography adjustments needed.

**Step 5: Commit**

```bash
git add index.html css/custom.css
git commit -m "polish: speaker notes, animations, responsive tweaks"
```

---

### Task 8: Create GitHub repo and push

**Step 1: Create the GitHub repo**

```bash
gh repo create dsifry/metaswarm-introduction-preso --public --source=. --push
```

**Step 2: Verify on GitHub**

Check that the repo is visible and the README renders correctly.
