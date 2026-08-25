# Roadmap

This roadmap tracks the progression of the `vlc-skins-high-dpi` research project from baseline analysis to final recommendations.

## Phase 1: Baseline & Research (Completed)

- [x] Establish project charter and design principles.
- [x] Analyze VLT format and extract official default skin source.
- [x] Document touch and High-DPI guidelines based on industry standards (Microsoft/GNOME/KDE).
- [x] Perform initial audit of default skin control dimensions.

## Phase 2: `default-touch` Prototype (In Progress)

- [x] Fork default skin to `skins/default-touch/`.
- [x] Implement touch-friendly XML layout (target sizes: 64x64 / 56x56).
- [ ] Produce high-resolution assets matching the new XML dimensions.
- [ ] Bundle and package as `.vlt`.
- [ ] Validate sizing and stability in VLC across various scaling factors.

## Phase 3: Validation & Measurement

- [ ] Measure effective pixel size of controls in the `default-touch` skin.
- [ ] Conduct usability testing on touch-enabled devices.
- [ ] Compare results against the baseline measurements.

## Phase 4: Final Reporting & Upstream Recommendations

- [ ] Synthesize findings into a final research report.
- [ ] Create a set of "High-DPI/Touch Best Practices" for VLC Skins2.
- [ ] Submit recommendations for upstream VLC UX improvements.
