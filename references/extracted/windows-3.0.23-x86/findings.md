# Findings

## Does default.vlt exist?

YES
Location: `references/skins-windows/default.vlt`
Evidence: File present in the `skins-windows` directory.

## Does VLC ship a reference skin?

YES
Details: The distribution includes `default.vlt` and `winamp2.xml` (though the latter is an XML file, it represents a reference skin style).

## Which shipped skin most closely resembles default VLC?

Candidate: `default.vlt`
Reasoning: As the primary shipped VLT, it serves as the baseline for the Skins2 system.

## Which shipped skin is most usable on high DPI displays?

Candidate: `default.vlt` (Baseline)
Reasoning: Without further analysis of other community skins, `default.vlt` is the only verified stable baseline provided in this release, although its current dimensions are likely too small for 4K.

## Which shipped skin is the best starting point?

Candidate: `default.vlt`
Justification: To create `default-touch`, we need to start with the "default" workflow. Using `default.vlt` ensures we preserve the familiar VLC layout while strictly modifying dimensions for touch and DPI targets.

## Questions

- Since `default.vlt` is a binary archive, we need to extract its internal XML to see the exact coordinate mapping of the controls.
- We need to determine if `winamp2.xml` provides a better structural example for modular components.
