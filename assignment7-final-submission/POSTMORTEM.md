# Assignment 7: Engineering Retrospective (Post-Mortem)

**Project:** Dreamscape — A Temporal Editing System for Memory and Thought
**Student:** Akanksha Patel | NetID: ap2490 | CS 428 | Spring 2026

---

## Pillar Overview & Achievements

Dreamscape is built on two primary pillars: **Procedural Generation** and **Rendering**.

For Procedural Generation, the core achievement is the adaptive spherical memory archive. Memories are distributed across one to four spherical shells using the Fibonacci golden-angle algorithm, which produces natural, even spacing without clustering. Frame scale adapts dynamically to archive density, and the frame textures themselves are procedurally generated at runtime using seeded canvas drawing — each memory gets a unique abstract art piece derived from its name and emotional tone. Particle systems (dust motes in both the hub and memory environments) are also procedurally driven.

For Rendering, the system runs a full post-processing pipeline: HDRI-based image-based lighting, ACES filmic tone mapping, and UnrealBloomPass for soft glow on emissive elements. The most meaningful rendering achievement is the five-tone memory atmosphere system — each tone (warm, cool, dream, echo, neutral) simultaneously drives fog color and density, sky gradient, window light color and intensity, bloom strength, and tone mapping exposure as one coherent shift. There is also an adaptive performance system with three quality tiers that scales pixel ratio and shadow resolution based on device capability.

Supporting pillars include Interaction & Navigation (first-person traversal, raycast-based object selection, real-time editing) and Animation (orbital frame motion, bezier camera transitions, walk bobbing, cinematic transition overlay).

---

## Playtest Resolution

The Assignment 6 user study identified four main issues. All were addressed in Assignment 7.

**Issue 1: Users were confused about controls and had no onboarding.**
The start screen now includes three explicit numbered steps explaining what to do. The controls hint panel inside the console was also rewritten to distinguish hub controls from memory controls clearly.

**Issue 2: Entering a memory produced a visible freeze.**
This was the most impactful fix. The enter memory flow now shows a fullscreen cinematic overlay — "DREAMSCAPE / reconstructing memory" — with a pulsing glow, drifting scanlines, cycling status text, and a progress bar tied to actual loading work. The overlay stays up for exactly as long as the system needs, then fades out cleanly when the bezier transition completes. What was a confusing freeze is now an intentional, branded moment.

**Issue 3: UI was inconsistent — buttons were always visible regardless of state.**
Enter Memory and Exit Memory buttons are now context-sensitive. Enter Memory only shows in the hub. Exit Memory only shows inside a memory. The edit tools panel is hidden during the transition and only revealed after it completes.

**Issue 4: Frames in the archive hub looked blank.**
Each frame now displays procedurally generated abstract art unique to that memory, driven by its tone and name. Warm memories get radiating golden light. Dream memories get dissolving violet blobs and a spiral. Echo memories get concentric ripple rings. Neutral memories get a star map with constellation lines. Tone changes update the frame art in real time.

---

## Technical Post-Mortem

**Biggest challenges:**

The hardest technical problem was cinematic camera control in WebGL. Getting OrbitControls to behave consistently across state transitions required careful tuning — bezier transitions, orbit target anchoring during WASD movement, and preventing damping velocity from carrying over between states all required iteration. The camera feeling wrong is immediately noticeable to any user, so this was high priority and high difficulty.

Performance was the other constant challenge. Every addition to the interior memory environment cost frames — higher-quality PBR materials, HDRI lighting, the exterior scene through the window, bloom post-processing, and particle systems all compete for GPU time. The adaptive performance system was built specifically to address this, but on lower-powered hardware (2017 MacBook Air with Intel HD Graphics 6000) the interior runs at approximately 20-25 FPS rather than the 60 FPS target defined in Assignment 2. On more capable hardware it performs closer to target.

**What was cut from the original vision:**

Several major features from the original Assignment 2 spec did not make it into the final build. The holographic console was intended to be fully interactive — a working interface for navigating the archive. In the final build it is a visual anchor only, with actual interactions handled through an HTML overlay panel. The exterior scene visible through the memory room window was planned as a navigable neighborhood environment. It exists in the final build as a simplified, non-explorable scene, deliberately kept low-complexity for performance reasons. Branching timelines and media uploads (image/audio input influencing visual style) were cut early and never revisited.

These cuts were necessary to ship a stable, complete interactive system rather than an unstable ambitious one. The course emphasis on building a real system over a visual demo guided these decisions.

---

## AI Tool Evaluation

AI tools were used throughout the semester for debugging, code review, architecture cleanup, and implementation of specific features — most notably the procedural frame texture system in the archive hub.

Where AI genuinely helped: debugging Three.js rendering issues, working through shader and post-processing math, cleaning up code structure, and accelerating boilerplate. Tasks that have a correct answer and a clear implementation path benefit most from AI assistance.

Where AI fell short: understanding and supporting the project vision. AI tools are effective at implementing what you describe but are not capable of understanding what you are trying to make feel like. The gap between "a working interactive 3D system" and "something that feels like you are actually reliving a memory" is a creative and design problem, not a technical one — and AI was not useful there. In several cases, AI-generated suggestions were technically functional but aesthetically wrong for the project, requiring significant revision or rejection. The lesson is that AI accelerates implementation but cannot substitute for taste, vision, or judgment about what the experience should feel like.
