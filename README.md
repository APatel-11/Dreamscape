# Dreamscape

Dreamscape is an interactive memory visualization environment where curated memory fragments orbit around the user inside a spherical archive.

Instead of browsing files or folders, the user stands at the center of a memory sphere where memories exist as floating frames. These frames can be selected, renamed, and explored using a holographic console interface.

This project is being developed as part of a **Computer Graphics course project at Rutgers University** and is currently in **Beta development**.

---

## Acknowledgments

I received debugging assistance from my tutor while working through issues with Three.js rendering, lighting, and scene composition.

The overall system design, interaction model, and final integrated build are my own work.

---

# Live Builds

## Assignment 5 — Beta Build

Expanded Dreamscape system introducing a fully interactive memory environment, enhanced rendering, and editable memory spaces.

Launch the build:

https://apatel-11.github.io/Dreamscape/assignment5-beta/

---

## Assignment 4 — Alpha Build

Interactive prototype demonstrating the Dreamscape memory hub, memory selection system, and console interface.

Launch the build:

https://apatel-11.github.io/Dreamscape/assignment4-alpha/

---

## Assignment 3 — MVP Prototype

Earlier prototype demonstrating the initial Dreamscape environment with particle fragments, timeline interaction, and performance HUD.

Launch the build:

https://apatel-11.github.io/Dreamscape/assignment3/

---

# Repository

GitHub Repository:

https://github.com/APatel-11/Dreamscape

---

# Project Overview

Dreamscape explores how memory could be visualized and interacted with in a spatial environment.

Users stand inside a spherical archive where memory fragments orbit around them. A holographic console allows users to interact with memories by editing names, entering memory states, and adjusting clarity.

The goal of the project is to experiment with **3D interfaces for navigating and editing personal memory archives**.

---

# Current System Features

## Game Loop

The current build implements a full interaction loop:

1. **Menu State**
   - Start screen introducing the experience

2. **Hub State**
   - User stands inside the Dreamscape sphere
   - Floating memory frames orbit around the user
   - Console allows interaction with memories

3. **Memory State**
   - Activated after selecting a memory
   - User enters a fully navigable memory environment

4. **Reset State**
   - User can return to the main menu

---

# Assignment 5 — Beta Build Features

The Beta Build expands Dreamscape into a **complete interactive system with rendering, interaction, and environmental depth**.

---

## Memory Environment (Rendering)

- Fully structured memory room (walls, ceiling, layout)
- Focal window acting as a visual anchor
- Lighting and material improvements
- Initial exterior environment visible through the window

---

## Interactive Editing System (Interaction)

- Add, remove, and transform objects inside the memory
- Real-time updates to the environment
- Interactive UI editing panel

---

## Archive System Expansion

- Memory count dynamically determines visual fragments
- Multi-shell spherical distribution prevents overcrowding
- Adaptive frame scaling maintains visual density

---

## Complete Interaction Loop

- Select memory from archive  
- Enter memory environment  
- Explore in first-person  
- Edit objects  
- Exit back to archive  

---

# Interaction Features

## Memory Sphere

Curated memory frames orbit around the user inside a spherical archive.

## Memory Selection

Users can click on floating frames to select a memory.

## Memory Console

The console allows the user to:

- Rename memories
- Save memory names
- Undo edits
- Enter a memory
- Exit memory view
- Reset the experience

## Timeline Control

A timeline slider adjusts the **clarity of the selected memory**, affecting environmental fog and visual atmosphere.

## Persistent Memory Names

Memory names are stored locally using **localStorage**, allowing edits to persist across sessions.

---

# Technologies Used

- Three.js
- WebGL
- JavaScript
- HTML
- CSS

Core systems implemented:

- interactive 3D rendering
- raycasting for object selection
- animation loop
- UI overlay system
- persistent memory storage

---

# Controls

## Mouse

Rotate camera — drag  
Zoom — scroll  
Select memory — click frame  

## Console Controls

Save Name  
Undo  
Enter Memory  
Exit Memory  
Reset Experience  

## Keyboard Shortcuts

R = save memory name  
U = undo last edit  
ESC = return to menu  

---

# Repository Structure

Dreamscape  
│  
├── assignment3  
│ └── index.html  
│  
├── assignment4-alpha  
│ └── index.html  
│  
├── assets  
│  
├── docs  
│  
└── README.md  

---

# Running the Project

## Option 1 — GitHub Pages

Assignment 5 Beta Build:  
https://apatel-11.github.io/Dreamscape/assignment5-beta/

Assignment 4 Alpha Build:  
https://apatel-11.github.io/Dreamscape/assignment4-alpha/

Assignment 3 MVP Prototype:  
https://apatel-11.github.io/Dreamscape/assignment3/

---

## Option 2 — Run Locally

Clone the repository:

git clone https://github.com/APatel-11/Dreamscape.git  

Open in a browser:

assignment5-beta/index.html  

---

# Known Limitations

This build is a **Beta prototype**.

- Low FPS in memory environments due to rendering complexity  
- Initial loading delay when entering a memory  
- Window rendering requires further refinement  
- Exterior environment is partially implemented  
- Particle system is stylized rather than physically accurate  

---

# Future Development

Planned improvements include:

- performance optimization (LOD, adaptive resolution)  
- improved spatial distribution  
- memory clustering and categorization  
- enhanced interaction tools  
- more realistic environments and lighting  

---

# Author

Akanksha Patel  
Computer Science  
Rutgers University  

GitHub:  
https://github.com/APatel-11  

---

# License

This project is currently for educational and research purposes.
