# Dreamscape

Dreamscape is an interactive memory visualization environment where curated memory fragments orbit around the user inside a spherical archive.

Instead of browsing files or folders, the user stands at the center of a memory sphere where memories exist as floating frames. These frames can be selected, renamed, and explored using a holographic console interface.

This project is being developed as part of a **Computer Graphics course project at Rutgers University** and is currently in **Alpha development**.

---

# Live Build

### Assignment 4 – Alpha Build

Interactive prototype demonstrating the Dreamscape memory hub and interaction system.

Launch the build here:

https://apatel-11.github.io/Dreamscape/assignment4-alpha/

Repository:

https://github.com/APatel-11/Dreamscape

---

# Project Overview

Dreamscape explores how memory could be visualized and interacted with in a spatial environment.

Users stand inside a spherical archive where memory fragments orbit around them. A holographic console allows users to interact with memories by editing names, entering memory states, and adjusting clarity.

The goal of the project is to experiment with **3D interfaces for navigating and editing personal memory archives**.

---

# Current Alpha Features

## Game Loop

The current build implements a basic interaction loop:

1. **Menu State**
   - Start screen introducing the experience

2. **Hub State**
   - User stands inside the Dreamscape sphere
   - Floating memory frames orbit around the user
   - Console allows interaction with memories

3. **Memory State**
   - Activated after selecting a memory
   - Environment shifts to focus on that memory

4. **Reset State**
   - User can return to the main menu

---

# Interaction Features

### Memory Sphere
Curated memory frames orbit around the user inside a spherical archive.

### Memory Selection
Users can click on floating frames to select a memory.

### Memory Console
The console allows the user to:

- Rename memories
- Save memory names
- Undo edits
- Enter a memory
- Exit memory view
- Reset the experience

### Timeline Control
A timeline slider adjusts the **clarity of the selected memory**, affecting environmental fog and visual atmosphere.

### Persistent Memory Names
Memory names are stored locally using **localStorage**, allowing edits to persist across sessions.

---

# Technologies Used

- **Three.js**
- **WebGL**
- **JavaScript**
- **HTML**
- **CSS**

Core systems implemented:

- interactive 3D scene rendering
- object selection via raycasting
- animation loop
- UI overlay system
- persistent memory storage

---

# Controls

### Mouse

- Rotate camera — drag
- Zoom — scroll
- Select memory — click frame

### Console Controls

- Save Name
- Undo
- Enter Memory
- Exit Memory
- Reset Experience

### Keyboard Shortcuts
R = save memory name
U = undo last edit
ESC = return to menu

---

# Repository Structure
Dreamscape
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

### Option 1 — GitHub Pages

Open the live alpha build:

https://apatel-11.github.io/Dreamscape/assignment4-alpha/

---

### Option 2 — Run Locally

Clone the repository:
git clone https://github.com/APatel-11/Dreamscape.git

Open the file:
assignment4-alpha/index.html

in a browser.

---

# Known Limitations

This build is an **early alpha prototype**.

Current limitations include:

- Memory environments are not fully implemented yet
- Some memory frames reuse placeholder content
- Console visuals are still experimental
- Timeline currently adjusts atmosphere only

---

# Future Development

Planned improvements include:

- Fully interactive memory environments
- Improved holographic console UI
- Particle-based memory reconstruction
- Dynamic memory content
- Expanded camera navigation
- Enhanced lighting and visual effects

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
