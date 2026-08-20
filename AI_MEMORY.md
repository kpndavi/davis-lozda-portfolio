# Project Context & AI Memory

Hello future AI (or Antigravity Agent)! 
This file was requested by the user to save the current state and architectural decisions of this project.

## Overview
This is a "Digital Library / Sandbox" personal portfolio. 
The aesthetic is an ultra-premium **"AI-built but with human touch"** design, utilizing dark mode, frosted glass (glassmorphism), elegant typography, and a living, physics-based UI.

## Architecture
This is a **100% static site** (HTML/CSS/JS only). It was intentionally built without heavy frameworks (Next.js/Turbopack caused issues earlier) to ensure it is bulletproof, easily hosted anywhere, and lightning fast.

### Core Technologies
1.  **D3.js (Force Graph)**: The core navigation UI is an interactive neural graph. The user's avatar is the central root node, and projects/thoughts orbit them using a physics simulation (gravity, collision). Nodes can be grabbed, dragged, and tossed elastically.
2.  **HTML DOM Nodes**: Instead of drawing raw Canvas shapes, D3 controls the `x` and `y` coordinates of standard HTML `<div>` elements. This allows the nodes to use CSS animations, `lucide` SVG icons, and complex frosted glass styling.
3.  **Static CMS (`knowledge.json`)**: All content (projects, books, thoughts) is decoupled from the HTML and loaded dynamically from `knowledge.json`. 
4.  **Marked.js**: When a node is clicked, a glass panel slides out from the right. The markdown content from `knowledge.json` is parsed by `marked.js` and rendered seamlessly in this panel.

## Key Files
- `index.html`: Contains all markup, **inline CSS** (inlined deliberately to prevent browser caching issues during rapid iteration), D3 graph initialization, and the panel slide-out logic.
- `knowledge.json`: The single source of truth for content. Add new nodes and links here. Uses Markdown for the body text.

## Future AI Instructions
- **CRITICAL:** DO NOT convert this back to React, Next.js, or any complex build system. The user explicitly rejected that approach in favor of this clean, static architecture.
- **COMMUNICATION:** Be direct and truthful. Never claim that a feature works unless it has actually been verified. Clearly distinguish facts from assumptions. If essential information is missing or unclear, ask the user a concise question instead of guessing.
- If modifying the layout or UI, preserve the `d3-force` logic. Ensure any new nodes are added to the simulation.
- Content updates should only be done by modifying `knowledge.json`. Do not hardcode new data into the HTML.
- Maintain the aesthetic: deep dark background, glowing ambient orbs (CSS animations), glassmorphism borders (`rgba(255,255,255,0.1)`), and the serif/sans-serif typography blend (`Instrument Serif` & `Inter`).
