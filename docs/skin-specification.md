# VLC Skins2 Specification

This document summarizes the technical specifications for creating and modifying VLC skins, extracted from official documentation.

## 1. Core Concepts

### Bitmaps

- **Format**: PNG is recommended for transparency and compatibility.
- **States**: Most controls require bitmaps for different states (e.g., Buttons: Up, Down, Mouseover).
- **Sub-Bitmaps**: A single image file can be divided into multiple `SubBitmap` regions using `x`, `y`, `width`, and `height` attributes.
- **Transparency**: Transparency is handled via the PNG alpha channel or a specified transparency color in the XML.

### The XML Structure

Skins follow a predefined DTD. The root element is `<Theme>`.

#### Key Elements

- **Theme**: Root element. Attributes: `version`, `alpha`, `movealpha`.
- **ThemeInfo**: Metadata about the skin (name, author, etc.).
- **Font**: Defines a font resource (`file` attribute).
- **Bitmap**: Defines an image resource (`file` attribute).
- **SubBitmap**: Defines a region within a `Bitmap`.
- **Window**: Defines a window (e.g., main window, playlist).
- **Layout**: Defines a specific arrangement of controls within a window.
- **Panel**: A container for other controls.
- **Group**: A way to group controls.

## 2. Layout Model (Nested Boxes)

VLC uses a "nested box" model for resizable windows.

### Box Types

- **Simple Boxes**: Individual controls (Image, Button, Checkbox, Text, Slider, etc.).
- **Container Boxes**: `Panel` and `Layout` tags. `Layout` is always the top-level box.

### Resizing Mechanisms

1. **Corners Anchoring**:
   - Controlled by `lefttop` and `rightbottom` attributes.
   - Ties the corners of the inner box to the corners of the container box (TL, TR, BL, BR).
   - Example: `TL/TL` and `BR/BL` means the inner box resizes vertically.
2. **Constant Ratio**:
   - Controlled by `xkeepratio` and `ykeepratio` attributes.
   - Maintains a constant ratio between the space on the top/bottom or left/right.
   - Overrides corners anchoring if set.

## 3. Interactivity

### Actions

Actions are triggered by controls (e.g., `action="vlc.play()"`). Multiple actions can be separated by `;`.

#### Common Actions

- `vlc.play()`, `vlc.pause()`, `vlc.stop()`
- `vlc.volumeUp()`, `vlc.volumeDown()`, `vlc.mute()`
- `vlc.fullscreen()`, `vlc.snapshot()`
- `playlist.next()`, `playlist.previous()`
- `dialogs.prefs()`, `dialogs.file()`

### Text Variables

Dynamic text can be inserted using escape sequences (starts with `$`):

- `$V`: Volume percentage.
- `$T`: Current time (H:MM:SS).
- `$L`: Remaining time.
- `$D`: Duration.
- `$N`: Stream name.

### Boolean Expressions

Controls can be shown/hidden dynamically using boolean expressions in attributes like `visible`.

- `vlc.isPlaying`, `vlc.isPaused`, `vlc.isStopped`
- `vlc.isFullscreen`, `vlc.isMute`
- `playlist.isRandom`, `playlist.isLoop`
- `WindowID.isVisible`
