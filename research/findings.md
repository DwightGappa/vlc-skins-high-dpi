# Findings

## VLT Format

VLT files are gzip-compressed tarballs.

### Structure

- **Payload**: A directory containing `theme.xml` and an assets folder (e.g., `subX/`).
- **theme.xml**: The main skin definition file (XML).
- **Assets**: Bitmaps (PNG), fonts (OTF), and other binary resources.

## VLC Default Skin Source

The default skin for VLC (Windows) is distributed as a VLT file, which is a compressed archive of the skin's source.

### Implications

- **Canonical Baseline**: We have the official default skin as a reference.
- **Editable Workflow**: Since the source is available as XML and individual assets, it can be modified directly without reverse engineering.
- **Development Path**: The "Default Touch" skin can be developed by forking the official default skin and adapting its layout and assets for high DPI and touch interactions.
