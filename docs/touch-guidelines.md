# Touch Interaction Guidelines

This document establishes the touch-targeting standards for the `vlc-skins-high-dpi` project. These guidelines ensure that the player remains usable on tablets, convertibles, and touch-enabled laptops.

## 1. Target Size Standards

### Minimum Target Size

Based on Microsoft's guidelines for targeting, the absolute minimum touch target for any interactive element is:

- **40 × 40 effective pixels (DIP)**

### Recommended Targets (Project Specific)

To account for the specific nature of media playback (where some controls are used more frequently or require higher precision), the following target sizes are recommended:

| Control | Target Size | Logic |
| :--- | :--- | :--- |
| **Play/Pause** | 64 × 64 | Primary action; must be effortless to hit. |
| **Next/Previous** | 56 × 56 | High-frequency navigation. |
| **Fullscreen** | 56 × 56 | Common utility. |
| **Volume Handle** | 56 × 56 | Requires sliding motion; larger area prevents slips. |
| **Seek Thumb** | 56 × 56 | Critical for precise timeline scrubbing. |
| **Seek Bar Height** | 28 px | Increased from 16-24px baseline to 28px for improved touch accessibility. |
| **Playlist Row** | 48–56 px | Prevents accidental selection of adjacent tracks. |

## 2. Interaction Principles

### Avoid Precision Dependence

Controls should not require "pixel-perfect" accuracy. If a control is small, it should be surrounded by sufficient padding to ensure the interactive area still meets the minimum target size.

### Low Precision Pointing

Design for the "fat finger" problem. Ensure that buttons are not clustered so tightly that a single touch triggers multiple actions.

### No Hover Reliance

Interactive elements must be clearly visible and distinguishable without relying on mouse-over/hover states to reveal their function.

## 3. Layout Considerations

- **Edge Padding:** Avoid placing critical controls too close to the screen edges, where palm rejection or bezel interference might occur.
- **Spacing:** Maintain a minimum gap of 8px between touch targets to reduce accidental triggers.
