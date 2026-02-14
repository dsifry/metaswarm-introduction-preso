# metaswarm Introduction Presentation — Design Document

**Date**: 2026-02-14
**Author**: Dave Sifry + Claude
**Status**: Approved

## Context

60-minute meeting for entrepreneurs and founders who have Claude Code but want to level up. Mixed technical levels. The presentation should be 15-20 minutes, leaving 40+ minutes for participatory hands-on work and Q&A.

## Core Message

**Quality at Speed** — You can move fast without breaking things. metaswarm gives you the processes of an elite engineering team, enforced automatically by AI agents.

## Design Principles

- **Show, don't tell** — GitHub contribution graph speaks louder than numbers
- **Humble, not braggy** — Let the work demonstrate the value
- **Participatory** — Most time spent with audience doing, not watching
- **Accessible** — The "just talk to Claude Code" DX works for everyone

## Presentation Framework

**Reveal.js** — Mature, markdown support, code highlighting, fragment animations. Custom dark theme.

## Visual Design

- **Background**: Deep charcoal (#1a1a2e)
- **Typography**: Inter (sans-serif), large headings, generous whitespace
- **Accent color**: Amber/gold (#f0b429) — warm, confident, not flashy
- **Code blocks**: Syntax-highlighted on slightly lighter dark panels, monospace
- **Animations**: Minimal — fade-ins and subtle slides only
- **Diagrams**: Simple SVG/CSS flows, clean lines, rounded corners
- **Overall feel**: Like a well-designed developer tool's landing page

## Slide Structure (16 slides, 3 acts)

### Act I — Context (2-3 min, 4 slides)

1. **Title** — "metaswarm" / "Quality at Speed" / Dave Sifry
2. **The Problem** — "Moving fast usually means cutting corners. What if your tools enforced quality automatically?"
3. **GitHub Contribution Graph** — Your actual GitHub activity graph. No numbers called out. Caption: "Built with metaswarm."
4. **What is metaswarm?** — One sentence: "An open-source orchestration framework that coordinates AI agents through a structured development workflow — from idea to merged PR."

### Act II — Show, Don't Tell (5-7 min, 6 slides)

5. **One command** — `npx metaswarm init` — terminal output visualization
6. **What you get** — Visual tree: agents, skills, commands, knowledge base
7. **The workflow** — 9-phase flow diagram with progressive reveal
8. **The key insight** — "Trust nothing, verify everything" — concrete example of orchestrator running tests independently
9. **It learns** — Knowledge base growth visualization
10. **Getting started is easy** — Transition to hands-on

### Act III — Let's Build Together (10-12 min, 6 slides)

11. **Prerequisites** — Claude Code + a project (new or existing)
12. **The friendliest install** — Open Claude Code, paste the metaswarm URL, say "install this for my project"
13. **What Claude set up** — Walk through the tailored scaffold
14. **Your first task** — Create a GitHub issue and start the workflow
15. **Watch the workflow** — Agents coordinate: research → plan → review → build → PR
16. **Resources & Q&A** — GitHub link, QR code, questions

## Technical Implementation

### Project Structure
```
metaswarm-introduction-preso/
├── index.html          # Main presentation file
├── css/
│   └── custom.css      # Custom theme overrides
├── images/
│   └── github-graph.png  # Contribution graph screenshot
├── package.json        # Minimal — just for repo metadata
├── README.md           # How to view/present
├── CLAUDE.md           # metaswarm project instructions
└── docs/
    └── plans/
        └── 2026-02-14-presentation-design.md
```

### Dependencies
- Reveal.js loaded via CDN (no build step needed)
- Inter font via Google Fonts
- No other runtime dependencies

### How to Present
- Open `index.html` in any modern browser
- Press `S` for speaker notes
- Arrow keys to navigate
- `F` for fullscreen
