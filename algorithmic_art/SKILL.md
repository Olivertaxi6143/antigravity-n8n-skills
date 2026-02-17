---
activation: model_decision
name: algorithmic-art
description: Create algorithmic art with p5.js, focusing on emergent behavior, mathematical beauty, and controlled chaos. Requires creating an Algorithmic Philosophy before implementation to ensure depth and craftsmanship.
---

# Algorithmic Art Creation

## 1. Algorithmic Philosophy Creation

To begin, create an ALGORITHMIC PHILOSOPHY (not static images or templates) that will be interpreted through:
- Computational processes, emergent behavior, mathematical beauty
- Seeded randomness, noise fields, organic systems
- Particles, flows, fields, forces
- Parametric variation and controlled chaos

### The Critical Understanding
- **What is received**: Some subtle input or instructions by the user to take into account, but use as a foundation; it should not constrain creative freedom.
- **What is created**: An algorithmic philosophy/generative aesthetic movement.
- **What happens next**: The same version receives the philosophy and EXPRESSES IT IN CODE - creating p5.js sketches that are 90% algorithmic generation, 10% essential parameters.

**Philosophy Requirements:**
- **Name the movement** (1-2 words): "Organic Turbulence" / "Quantum Harmonics" / "Emergent Stillness"
- **Articulate the philosophy**: 4-6 paragraphs capturing the ALGORITHMIC essence.
- **Emphasize craftsmanship**: Stress that the algorithm appears to be the product of deep computational expertise and painstaking optimization.
- **Leave creative space**: Be specific about direction but allow room for high-level implementation choices.

## 2. p5.js Implementation

### ⚠️ STEP 0: READ THE TEMPLATE FIRST ⚠️
**CRITICAL: BEFORE writing any HTML:**
1. **Read** `templates/viewer.html`
2. **Study** the structure and Anthropic branding
3. **Use that file as the LITERAL STARTING POINT**
4. **Keep all FIXED sections exactly as shown**
5. **Replace only the VARIABLE sections**

### Technical Requirements
- **Seeded Randomness**: ALWAYS use a seed (`randomSeed(seed)`, `noiseSeed(seed)`) for reproducibility.
- **Parameter Structure**: Define `params` distinct from the algorithm logic.
- **Core Algorithm**: Express the philosophy through code (accumulation, geometric ratios, feedback loops). not generic patterns.

### Craftsmanship Requirements
- **Balance**: Complexity without noise.
- **Color Harmony**: Thoughtful palettes.
- **Composition**: Visual hierarchy and flow.
- **Performance**: Smooth execution.
- **Reproducibility**: Same seed = Identical output.

## 3. Interactive Artifact Creation

### Critical: What's Fixed vs Variable
- **FIXED (Do not change)**:
    - HTML Structure (Sidebar + Main Canvas)
    - CSS Styling (Fonts, Colors, Spacing)
    - Seed Input & Control
    - "New Seed" & "Download" Buttons
    - Logo & Branding

- **VARIABLE (Your creative canvas)**:
    - The `setup()` and `draw()` functions
    - The `generate()` function
    - The `params` object configuration
    - The specific UI sliders/inputs for YOUR parameters

### Required Features
1. **Resizability**: Canvas must resize with window/container.
2. **Parameter UI**: Create HTML inputs for your specific params in the sidebar.
3. **Instant Feedback**: Updating params updates art immediately (or on release).
4. **High-Res Export**: Download button saves high-res PNG.

### Using the Artifact
- The output is a single HTML file containing the p5.js sketch and UI.
- Users can tweak parameters and seeds to explore the "infinite gallery" of your algorithm.