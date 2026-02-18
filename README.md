# Dreamscape (CS 428/523)

Dreamscape is a web-based 3D visualization prototype exploring temporal editing of an abstract “memory/dream” environment. This repository contains work for multiple assignments.

## Assignment 3 — MVP Prototype

**Core MVP mechanic:** A timeline slider (rewind/fast-forward) that drives real-time visual transformations in a 3D dreamscape (fog density, geometry distortion, and particle motion).

### Live Demo (GitHub Pages)
- MVP link: https://apatel-11.github.io/Dreamscape/assignment3-mvp/dreamscape_mockup.html

### How to Run Locally
**Option A (quickest):**
1. Download or clone this repository.
2. Open `assignment3-mvp/dreamscape_mockup.html` in Google Chrome.

**Option B (recommended): run a local web server**
1. In the repo folder, run:
   - `python3 -m http.server 8000`
2. Open in your browser:
   - `http://localhost:8000/assignment3-mvp/dreamscape_mockup.html`

### Controls
- Timeline slider: changes fog density, geometry scaling, and particle motion in real time.
- (Camera): fixed camera in MVP mockup.

### Notes
- Tested in Chrome.
