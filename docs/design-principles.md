# Design Principles

This document outlines the core design philosophy for the `vlc-skins-high-dpi` project, ensuring consistency across all prototype skins.

## 1. Touch-First Ergonomics

- **Target Prioritization:** Controls are prioritized based on usage frequency. Primary playback controls (Play/Pause) receive the largest targets, followed by secondary navigation (Next/Prev).
- **Low-Precision Padding:** We implement generous padding around interactive elements to ensure that "fat-finger" interactions do not trigger unintended adjacent controls.
- **Visual Affordance:** Controls must be visually distinct and their purpose clear without relying on hover states, which are non-existent in touch interfaces.

## 2. Scaling and Density

- **Adaptive Dimensions:** Use relative scaling (`keepratio`) where possible to ensure that the UI feels consistent across 150%, 200%, and 300% scaling factors.
- **Asset Fidelity:** Assets are developed at high resolutions to prevent blurring when scaled up on 4K displays.
- **Density Balance:** While increasing target sizes for touch, we aim to maintain a balance that doesn't make the interface feel overly sparse or waste screen real estate.

## 3. Consistency and Familiarity

- **Workflow Preservation:** The layout follows the established VLC Skins2 logic to ensure that users of the default skin can transition to the touch version with zero learning curve.
- **Standardized Targets:** Adhere strictly to the project's internal touch target table (e.g., 64x64 for primary, 56x56 for secondary).
