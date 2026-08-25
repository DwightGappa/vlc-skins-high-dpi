# Project Charter: vlc-skins-high-dpi

## 1. Purpose
The `vlc-skins-high-dpi` project is a usability and accessibility research initiative. It aims to investigate how the VLC Media Player interface can be optimized for modern display environments, specifically focusing on High-DPI (4K+) screens and touch-enabled devices.

The project uses the VLC Skins2 system as a rapid prototyping environment to test and document UX improvements that could potentially inform future upstream developments in the VLC project.

## 2. Objectives
- **Baseline Measurement:** Document the existing control dimensions and usability hurdles of the default VLC UI on high-resolution displays.
- **Touch-First Prototyping:** Implement skin layouts that adhere to modern touch target standards (minimum 40x40 DIP).
- **Scaling Validation:** Test and validate UI layouts across multiple scaling factors (150%, 200%, 300%) to ensure consistency and accessibility.
- **Cross-Platform research:** Validate that proposed improvements work across Windows and Linux (GNOME/KDE) environments.
- **Upstream Recommendations:** Produce a detailed findings report with concrete recommendations for the VLC community.

## 3. Project Principles
- **Input Agnostic:** The UI should be equally usable via mouse, touch, or other pointing devices.
- **Touch Friendly:** Controls must be sized for low-precision input.
- **High-DPI Friendly:** Assets and layouts must scale without losing clarity or usability.
- **Simple by Default:** Maintain the "Simple by default, powerful when needed" philosophy inspired by KDE.
- **Preserve VLC Familiarity:** Improvements should enhance the existing workflow, not replace it with an alien UX.

## 4. Success Criteria
- Completion of the `default-touch` MVP skin.
- A comprehensive report documenting the measured improvement in touch target sizes and seek-bar usability.
- Verification of layout stability across three major OS/Desktop environment combinations.

## 5. Non-Goals
- This is NOT a project to recreate the retired VLC UWP application.
- This is NOT a project to create a standalone media player or fork VLC.
- This is NOT a project to implement a specific design language (e.g., Fluent Design).
