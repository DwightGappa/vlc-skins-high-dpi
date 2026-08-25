# Agent Operational Guide: /docs

This guide provides instructions for autonomous agents and LLMs interacting with the documentation folder.

## 🎯 Contextual Role

The `/docs` folder is the **source of truth** for project constraints. All proposed skin modifications or research tasks must be validated against these documents.

## 🛠 Operational Workflows

### 1. Validating a UI Change

When proposed a change to a skin (`.vlt`):

1. Read `docs/touch-guidelines.md` to verify the target size meets the minimum 40x40 DIP requirement.
2. Read `docs/high-dpi-guidelines.md` to ensure the change is validated across 150%-300% scaling.
3. Reference `docs/project-charter.md` to ensure the change does not drift into "Non-Goals" (e.g., attempting to clone Fluent Design).
4. Compare against structural baselines in `references/skins-windows/` and the technical spec in `references/skins2-create.html`.

### 2. Initiating New Research

When tasked with measuring a control:

1. Use `docs/research-measurement-template.md` as the structure for the findings report.
2. Compare results against the "Recommended Targets" table in `docs/touch-guidelines.md`.

### 3. Updating Documentation

Documentation updates should occur when:

- New research findings necessitate a change in the "Recommended Targets".
- The Project Charter is amended by the user.

## ⚠️ Critical Constraints

- **Reference Isolation:** Any files or directories under `references/` are for reference only. Do not modify them.
- **Skin Forking:** When basing a new skin on a reference skin, you must fork the skin base from the `references/` folder into its own dedicated folder within the `skins/` directory.- **Do not hallucinate targets:** Only use the dimensions specified in the guidelines.
- **Constraint over Feature:** Prioritize the Project Charter's non-goals over feature requests that contradict them.
