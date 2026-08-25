# vlc-skins-high-dpi

**High-DPI and touch-friendly skins for VLC Media Player focused on usability, accessibility, and modern display support.**

## Overview

`vlc-skins-high-dpi` is a usability and accessibility research project that uses VLC Skins2 as a rapid prototyping platform. The goal is to design and implement media player interfaces that remain functional and comfortable on modern high-resolution displays and touch-enabled devices.

Rather than focusing on a specific technology stack, this project prioritizes the *user experience*—specifically addressing the common issue where VLC's controls can feel too small on 4K displays or difficult to manipulate via touch.

## Project Principles

- **Input Agnostic:** Works seamlessly with mouse, touch, and other pointing devices.
- **Touch Friendly:** Adheres to modern touch target guidelines (e.g., Microsoft's ~40x40 DIP).
- **High-DPI Friendly:** Scales gracefully across 150%, 200%, and 300% scaling settings.
- **Cross Platform:** Aims for compatibility across Windows, Linux (KDE/GNOME), and other supported platforms.
- **Accessibility First:** Prioritizes visibility, contrast, and ease of interaction.
- **Preserve VLC Familiarity:** Enhances the experience without breaking the core VLC workflow.
- **Simple by Default:** Powerful when needed, but uncomplicated for the average user.

## Goals & Non-Goals

### ✅ Goals

- Research and prototype high-DPI improvements for VLC Skins2.
- Establish touch target baselines for media player controls.
- Create a "default-touch" skin that adapts the standard VLC workflow for modern hardware.
- Document findings to provide recommendations for future upstream VLC UX improvements.

### ❌ Non-Goals

- Recreating the retired VLC UWP/WinRT application.
- Cloning Fluent Design or creating a Windows-only skin.
- Replacing VLC, forking the project, or creating a standalone media player.

## Repository Structure

- `docs/`: Project charter, research guidelines, and findings.
- `research/`: Documentation and data gathered from Microsoft, GNOME, KDE, and VLC.
- `skins/`: The prototype `.vlt` skins (e.g., `default-touch`).
- `screenshots/`: Baseline vs. improved UI comparisons.
- `tools/`: Utilities for skin development and measurement.

## Getting Started

See [CONTRIBUTING.md](CONTRIBUTING.md) for information on how to contribute to this research effort.
