# Boomy Pixel Painter

A browser-based pixel art editor for creating LED matrix displays compatible with matrix displays

Primarily designed for use with [UMP](https://github.com/suchyindustries/UnexpectedMatrixPixels/tree/main) and Home Assistant

## Features

- **Interactive Grid**: Draw pixel art on customizable grid sizes (up to 96×96)
- **Color Wheel Picker**: Advanced HSL color selector with visual preview
- **8-Color Palette**: Quick-access swatches with automatic color detection
- **Drawing Tools**:
  - Left-click to paint individual pixels
  - Right-click to flood-fill areas
  - Eraser tool (press `X` or click the X button)
- **Undo/Redo**: Full history support (up to 50 steps)
  - `Ctrl+Z` to undo
  - `Ctrl+Y` to redo
- **YAML Export**: Generates Home Assistant service call YAML
- **PNG Export**: Save your artwork as an image file
- **Import/Export**: Load existing YAML pixel data

## Usage

1. **Open** `idotmatrix.html` in any modern browser
2. **Set** your entity ID (e.g., `display_7b3db4`)
3. **Configure** grid size (width × height)
4. **Draw** your pixel art using the color palette or colour wheel
5. **Copy** the generated YAML output for use in Home Assistant automations or scripts

## YAML Output Format

The tool generates YAML in this format:

```yaml
target:
  entity_id: light.display_7b3db4
data:
  elements:
    - type: pixels
      pixels:
        - [x, y, r, g, b]
        - [x, y, r, g, b]
        # ...
action: ump.draw_visuals
```

Use this in Home Assistant scripts or automations to display your pixel art on compatible LED matrix devices.

## Keyboard Shortcuts

- `Ctrl+Z` — Undo
- `Ctrl+Y` — Redo  
- `X` — Activate eraser tool

