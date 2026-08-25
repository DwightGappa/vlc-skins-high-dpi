# Documentation Directory Index

This directory contains the foundational research, guidelines, and charters for the `vlc-skins-high-dpi` project. These documents serve as the authoritative source for design decisions and validation metrics.

## 📄 Core Documents

- **[Project Charter](project-charter.md)**: The "Why" and "What". Defines the project's purpose, objectives, success criteria, and strict non-goals.
- **[Touch Interaction Guidelines](touch-guidelines.md)**: Design standards for touch targets. Specifies minimum and recommended dimensions (e.g., 40x40 DIP) to ensure accessibility on tablets and touch-enabled laptops.
- **[High-DPI Display Guidelines](high-dpi-guidelines.md)**: Strategy for scaling and visual clarity. Covers validation across 150%, 200%, and 300% scaling factors.
- **[Research Measurement Template](research-measurement-template.md)**: The standardized format for documenting UI control measurements and comparing them against baselines.

## � External References

- **[/references](../references/)**: Contains original VLC binary skins and official Skins2 creation documentation. Use these as the structural baseline for all prototypes.

## �🛠 How to Use This Folder

- **For Designers:** Use the `touch-guidelines.md` and `high-dpi-guidelines.md` as the primary specification for any new skin prototypes.
- **For Researchers:** Use the `research-measurement-template.md` to ensure all data gathered is consistent and comparable.
- **For Agents/LLMs:** Reference the `project-charter.md` to understand the boundaries of the project (Non-Goals) before proposing changes.
