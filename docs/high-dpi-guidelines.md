# High-DPI Display Guidelines

This document outlines the approach for ensuring the `vlc-skins-high-dpi` project remains visually clear and usable across various display densities and scaling factors.

## 1. Scaling Strategy

### Target Scaling Factors

The project validates skins against the following common Windows/Linux scaling settings:

- **150%** (Common on 13-15" 1080p/1440p laptops)
- **200%** (Standard for many 4K displays)
- **300%** (Common on high-density tablets and small 4K screens)

### Asset Resolution

To avoid blurriness on high-density screens, assets should be provided at multiple resolutions or implemented using techniques that resist scaling artifacts.

- Prefer high-resolution source assets.
- Ensure that iconography remains sharp and recognizable at 2x and 3x scale.

## 2. Visual Usability

### Typography

- **Readability:** Use system fonts that scale natively with the OS.
- **Sizing:** Ensure text does not become disproportionately small relative to the controls when scaling is applied.
- **Contrast:** Maintain high contrast ratios to ensure legibility on screens with varying brightness and calibration.

### Spacing & Proportions

- **Relative Spacing:** Use spacing that scales proportionally.
- **Avoid Hardcoded Pixel Limits:** Where possible in the Skins2 XML, avoid layouts that "break" or overlap when elements expand due to scaling.

## 3. Validation Process

### Baseline Comparison

Every proposed skin modification should be compared against the default VLC UI at the same scaling factor.

- **Measure:** Use screen-capture tools to measure the resulting effective pixel size of controls.
- **Verify:** Ensure that a 40x40 DIP target at 100% scaling remains a comfortable target at 200% scaling.

### Multi-Environment Testing

Testing must be performed on:

- Windows (various scaling factors).
- Linux KDE (Plasma scaling).
- Linux GNOME (Fractional scaling).
