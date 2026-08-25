# Project Plan: vlc-skins-high-dpi

## 🎯 Goal

Improve VLC usability on modern high-DPI and touch-enabled devices while preserving the existing VLC workflow and cross-platform nature using Skins2 as a prototyping platform.

## 🛠 Phase 0: Repository Archaeology (Completed)

- [x] Initialize repository and bootstrap scaffolding.
- [x] Establish baseline commit and `repo-bootstrap` branch.
- [x] Inventory VLC 3.0.23 Windows x86 skins.
- [x] Analyze Skins2 architecture and `default.vlt` structure.
- [x] Document findings and validate the `default-touch` MVP hypothesis.
- [x] Identify critical controls requiring modification (Play/Pause, Seek Bar, Playlist).

## 🎨 Phase 1: default-touch Prototype (Active)

### implementation Plan: Default-Touch Skin

The goal is to create the `default-touch` skin by forking the official VLC default skin and adapting it for High-DPI screens and touch interactions, adhering to the 40x40 DIP minimum target standard.

**Steps**

1. **Baseline Extraction**
   - Copy the extracted `references/skins-windows/default` directory to `skins/default-touch/source`.
2. **Asset Analysis & High-Res Sourcing**
   - Audit `skins/default-touch/source/subX/main.png` to identify all existing controls.
   - Determine if current assets can be scaled or if new, high-resolution versions are needed to avoid blurriness (per `docs/high-dpi-guidelines.md`).
3. **Touch-Target Layout Design (XML) [Alpha Phase]**
   - Modify `skins/default-touch/source/theme.xml` to implement touch-friendly sizing.
   - **Priority Controls**:
     - Increase Play/Pause to 64x64.
     - Increase Next/Prev, Fullscreen to 56x56.
     - Expand Seek Thumb and Volume Handle to 56x56.
     - Set Seek Bar height to 28px.
   - **Spacing**: Implement minimum 8px gaps between targets.
   - **Anchoring**: Transition from fixed coordinates to the "Nested Box" model using `lefttop`, `rightbottom`, and `keepratio` to ensure stability across scaling factors (150%, 200%, 300%).
4. **Geometry Validation [Alpha Deliverable]**
   - Bundle the source with existing assets (stretched) into a `.vlt` package.
   - Load in VLC to verify that new hit-targets do not cause overlap or layout breakage.
5. **Asset Production [Beta Phase]**
   - **Tier 1 (Vector/SVG)**: Redraw primary controls (Play, Pause, Stop, Next, Prev, Seek/Vol thumbs) to match XML dimensions.
   - **Tier 2 (Refinement)**: Update secondary controls (Mute, Shuffle, etc.).
   - **Tier 3 (Raster)**: Update backgrounds and frames.
   - Ensure transparency is correctly handled.
6. **Packaging & Final Verification**
   - Bundle the source with high-res assets into a final `.vlt` file.
   - Place the resulting bundle in `skins/default-touch/builds/`.
   - Validate touch target sizes using screen-capture measurements.
   - Verify layout stability at 100%, 200%, and 300% Windows scaling.

**Relevant files**

- `references/skins-windows/default/theme.xml` — Reference baseline XML.
- `skins/default-touch/source/theme.xml` — Target XML for modification.
- `skins/default-touch/source/subX/main.png` — Target bitmap for updates.
- `docs/touch-guidelines.md` — Target size requirements.
- `docs/skin-specification.md` — Technical implementation details.

**Verification**

1. **Visual Audit**: Confirm no overlapping controls at 300% scaling.
2. **Size Validation**: Measure Play/Pause button $\ge$ 64x64 effective pixels.
3. **Functional Test**: Ensure all actions (play, pause, seek) trigger correctly with the new layout.

**Decisions**

- **Fork Strategy**: Start with the official default skin to maintain familiarity.
- **Asset approach**: Prefer high-res replacements over simple scaling to maintain clarity.
- **Layout approach**: Use the nested box model to future-proof against various display sizes.

## 🖥️ Phase 2: default-4K Optimization

- [ ] **Asset Upgrade**: Implement higher resolution assets to prevent blurriness.
- [ ] **Typography**: Optimize font sizes and contrast for 4K displays.
- [ ] **Spacing**: Fine-tune layout proportions for ultra-high resolution.

## 📊 Phase 3: Research Reporting & Upstreaming

- [ ] **Comparison**: Document baseline VLC vs. HDPI skins with measured improvements.
- [ ] **Recommendations**: Prepare a findings report for the VLC community.
- [ ] **Validation**: Verify across Windows, Linux (KDE), and Linux (GNOME).

## ⚠️ Constraints & Non-Goals

- ❌ Not a VLC fork or replacement.
- ❌ Not a Windows 11 / Fluent Design clone.
- ❌ Not a UWP recreation.
- ❌ No implementation until research findings are complete.

## 📝 Revert Strategy

- Baseline Commit: `a0b28a5`
- Reset: `git reset --hard a0b28a5`
- Clean: `git clean -fd`
