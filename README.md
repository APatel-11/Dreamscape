# Dreamscape

**An interactive 3D memory archive built with Three.js.**

Dreamscape is a web-based interactive system that reimagines memory as a navigable, editable space. Instead of browsing files or folders, the user stands at the center of a holographic archive where memories orbit around them as floating frames. Selecting a memory transports the user — through a cinematic camera transition — into a fully navigable first-person interior, where they can walk around, examine objects, and edit the environment in real time.

The project explores how internal mental experiences (memory, mood, atmosphere) can be expressed through procedural generation, real-time rendering, and direct interaction.

🔗 **Live Final Build(In Progress):** [https://apatel-11.github.io/Dreamscape/](https://apatel-11.github.io/Dreamscape/)

🔗 **Live Build:** [https://apatel-11.github.io/Dreamscape/assignment7-final-submission](https://apatel-11.github.io/Dreamscape/assignment7-final-submission)

🔗 **Repository:** [https://github.com/APatel-11/Dreamscape](https://github.com/APatel-11/Dreamscape)

---

## Project Overview

Dreamscape was developed as a semester-long solo project for **CS 428/523: Interactive Computer Graphics** at Rutgers University (Spring 2026). It demonstrates a complete interactive system, not a tech demo — the user moves through a deliberate sequence of states (menu → archive → memory → exit) with persistent state, editable content, and cinematic transitions throughout.

The project shifted from an early concept of abstract particle visualization (Assignment 3) to a structured, immersive system in which memories are spatial environments that respond to user input.

---

## Computer Graphics Pillars

This project is built on two primary pillars from the course:

### 1. Procedural Generation
- The memory archive procedurally distributes memory frames across one to four spherical shells based on the number of memories, using the Fibonacci / golden-angle distribution to avoid clustering
- Adaptive frame scaling based on archive density
- Procedurally generated painting textures (canvas-based) inside the memory environment
- Procedural particle (dust mote) systems in both the archive and memory environments

### 2. Rendering
- Real-time PBR-style rendering using Three.js with HDRI-based environment lighting
- Custom-tuned dynamic lighting system inside memory environments (warm/cool/dream/echo/neutral tones, each with their own light color, intensity, fog, and bloom curves)
- Post-processing pipeline: ACES filmic tone mapping + Unreal Bloom
- Adaptive performance system (high / balanced / performance modes that adjust pixel ratio, shadow map size, and bloom)
- Bezier-curve cinematic camera transitions between hub and memory states

### Supporting Pillars
- **Interaction & Navigation:** First-person WASD navigation, raycast-based object selection, real-time editing (move/rotate/scale/add/remove)
- **Animation:** Frame orbital motion, walk bobbing, console scanlines, particle drift, and cinematic camera animation

---

## Core Features

### Game Loop
1. **Menu** — start screen with onboarding instructions
2. **Hub** — the holographic memory archive, where the user stands inside a sphere of orbiting memory frames
3. **Memory Transition** — cinematic camera bezier into the selected memory, with a custom "reconstructing memory" loading overlay
4. **Memory** — first-person interior, fully navigable, with real-time object editing
5. **Exit** — return to the hub

### The Holographic Console
A custom 3D console (built from procedural geometry, not images) sits in the center of the archive and acts as the system's narrative anchor. It displays animated waveforms, scanlines, pulse bars, glowing accents, and the title "DREAMSCAPE | MEMORY ARCHIVE". The actual interaction controls are provided through a synced HTML overlay panel.

### Memory Editing
Inside each memory the user can:
- Add new objects (10 object types: cubes, spheres, plants, lamps, vases, crystals, memory pillars, etc.)
- Select objects by clicking; selected objects glow cyan
- Move (arrow keys), rotate (W/E), scale (Q/R), or delete (Backspace)
- All edits persist per-memory, per-session via `localStorage`

### Memory Tone System
Each memory has a "tone" (warm / cool / dream / echo / neutral) that drives the entire scene's:
- Fog color and density
- Window light color and intensity
- Sky gradient
- Bloom strength and threshold
- Tone mapping exposure

Cycling tones via the console produces a coherent, dramatic atmospheric shift, not just a color swap.

### Cinematic Transition Overlay
The transition into a memory uses a layered cinematic overlay:
- Pulsing radial glow with cyan-violet-pink gradient
- Drifting holographic scanlines
- Cycling status text ("accessing archive" → "resolving spatial structure" → "reconstructing memory")
- Live progress bar tied to actual loading work + bezier transition progress
- Subtle vignette and film grain

The overlay is **dynamic** — it stays up exactly as long as the system needs to load, then fades cleanly when the bezier camera completes its arc into the memory.

### Persistent Memory Archive
- Memory names, tones, clarity values, and edited objects all persist in `localStorage`
- The archive can be expanded (Add Memory), pruned (Erase Memory), or fully reset

---

## Technologies

| Layer | Tools |
|---|---|
| Engine | Three.js (r128) + WebGL |
| Language | JavaScript (vanilla) |
| Markup / Style | HTML5, CSS3 |
| 3D Models | glTF 2.0 (.glb) |
| Textures | PBR maps (diffuse / normal / roughness) |
| Environment | HDRI (`.hdr`) for realistic lighting |
| Post-processing | EffectComposer, UnrealBloomPass, RenderPass |
| Storage | Browser `localStorage` |

### External Three.js Modules Used
- `OrbitControls` — camera control
- `GLTFLoader` — model loading
- `RGBELoader` — HDRI environment maps
- `RectAreaLightUniformsLib` — area light support
- `EffectComposer` + `UnrealBloomPass` — post-processing pipeline

---

## Controls

### Hub (Memory Archive)
| Action | Control |
|---|---|
| Orbit camera | Drag |
| Adjust clarity | Scroll wheel / timeline slider |
| Select memory | Click a floating frame |
| Enter selected memory | Click `Enter Memory` button |

### Memory (First-Person Interior)
| Action | Control |
|---|---|
| Walk | `W` `A` `S` `D` |
| Look around | Drag |
| Select object | Click |
| Move object | Arrow keys |
| Rotate object | `W` / `E` |
| Scale object | `Q` / `R` |
| Delete object | `Delete` / `Backspace` |
| Exit memory | Click `Exit Memory` button |

### Global
| Action | Control |
|---|---|
| Save memory name | `R` |
| Undo memory name | `U` |
| Return to menu | `ESC` |

---

## Repository Structure

```
Dreamscape/
├── assets/
│   ├── hdri/                      # HDRI environment maps
│   ├── models/                    # .glb 3D models (desk, sofa, bookshelf, etc.)
│   └── textures/                  # PBR texture sets
│
├── assignment3-mvp/               # Midterm MVP (procedural temporal slice)
├── assignment4-alpha/             # Alpha build (full game loop + memory hub)
├── assignment5-beta/              # Beta build (interior + editing system)
├── assignment6-feature-complete/  # Feature-complete build (peer playtested)
├── assignment7-final-submission/  # Final build (polish + cinematic transition)
│
├── index.html                     # Repo landing page
└── README.md
```

---

## Running the Project

### Option 1 — GitHub Pages (Recommended)
Each milestone has a deployed live build:

| Milestone | Live URL |
|---|---|
| **Final Submission** | [assignment7-final-submission/](https://apatel-11.github.io/Dreamscape/assignment7-final-submission/) |
| Feature Complete | [assignment6-feature-complete/](https://apatel-11.github.io/Dreamscape/assignment6-feature-complete/) |
| Beta Build | [assignment5-beta/](https://apatel-11.github.io/Dreamscape/assignment5-beta/) |
| Alpha Build | [assignment4-alpha/](https://apatel-11.github.io/Dreamscape/assignment4-alpha/) |
| MVP Prototype | [assignment3-mvp/](https://apatel-11.github.io/Dreamscape/assignment3-mvp/) |

### Option 2 — Run Locally
Because the project loads textures, models, and HDRIs from the local file system, it must be served from an HTTP server (not opened directly via `file://`).

```bash
git clone https://github.com/APatel-11/Dreamscape.git
cd Dreamscape
python3 -m http.server 8000
```

Then open: `http://localhost:8000/assignment7-final-submission/`

---

## Development Milestones

| Assignment | Milestone | Key Outcome |
|---|---|---|
| 1 | Group Formation & Concept | Project pillars selected, narrative concept defined |
| 2 | PRD, Tech Spec & MVP Definition | Approved by Prof. Kapadia, mentor (Sen) assigned |
| 3 | MVP Implementation | Procedural temporal-edit prototype with timeline + particles |
| 4 | Production Plan & Alpha Build | Full game loop (menu → hub → memory) and memory selection |
| 5 | Beta Build | Interior memory environment, editing system, lighting upgrade |
| 6 | Feature Complete & Peer Playtesting | Performance system, traversal stability, 5+ subject user study |
| 7 | Final Submission | Cinematic transition overlay, UI cohesion, camera polish, applied playtest feedback |

---

## Performance Notes

The project targets **60 FPS** in modern desktop browsers (Chrome / Firefox / Safari / Edge). The performance system automatically calibrates pixel ratio, shadow resolution, and bloom radius based on the active mode. Initial load may take 2–3 seconds while HDRI, textures, and `.glb` models load — this is buffered behind the `Start Dreamscape` button (which stays disabled until all assets are ready).

---

## Known Limitations

- Some collision edge cases near walls (player can occasionally clip slightly into wall trim)
- Mobile / touch interaction is not optimized — desktop is the intended platform
- Initial memory entry has a brief load — masked by the cinematic overlay
- Exterior scene through the window is intentionally simplified for performance

---

## Acknowledgments

- **Course:** CS 428/523 Interactive Computer Graphics — Rutgers University, Spring 2026
- **Instructor:** Professor Mubbasir Kapadia
- **TA / Mentor:** Sen
- **TA:** Danrui Li
- 3D models and PBR textures from open-source asset libraries (used under their respective licenses)
- AI tools (Claude, ChatGPT) were used for debugging assistance, code review, and concept review. All design decisions, system architecture, and integration are my own work.
- Tutor was also consulted for code review and concept clarification

---

## Author

**Akanksha Patel**
Computer Science, Rutgers University
NetID: ap2490
GitHub: [@APatel-11](https://github.com/APatel-11)

---

## License

This project was developed for educational purposes as part of CS 428/523 coursework at Rutgers University.
