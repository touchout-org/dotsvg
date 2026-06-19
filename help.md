# DotSVG Help

## About the DotPad Keys

The DotPad has six keys arranged like a Perkins braille keyboard: three on the left hand (dots 1, 2, 3, from index finger inward) and three on the right hand (dots 4, 5, 6, from index finger inward). This documentation refers to keys by their Perkins dot number. Commands use individual dots and chords (multiple dots pressed simultaneously), corresponding to the braille characters those dot patterns represent.

## Cursor Movement

- **dot 3** — move left
- **dot 6** — move right
- **dot 2** — move up
- **dot 5** — move down

Movement accelerates: first 3 presses = 1 px, presses 4–6 = 5 px, press 7+ = 10 px. Any other key resets acceleration.

- **dot 4** — jump to next object (top-left → bottom-right)
- **dot 1** — jump to previous object
- **v** — toggle cursor visibility

## Zoom & Pan

- **dots 5+6** — zoom in (halve viewport)
- **dots 2+3** — zoom out (double viewport)
- **o** — overview: full canvas with dashed viewport outline; any key returns

## Selection

- **s** — toggle selection on object under cursor (multi-select supported)

Selected objects appear with solid fill. Smaller unselected objects punch through the filled region.

## Edit Menu (e)

Press **e** to open the Edit Menu for the current object. Navigate with **dot 6** / **dot 3**; confirm with **dot 4** or **dot 5**; cancel with **dot 1** or **dot 2**.

Actions: **delete**, **rename**, **move**.

### Move mode

- **dot 3 / dot 6 / dot 2 / dot 5** — move 1 px per press
- **dot 1** — rotate 15° counter-clockwise
- **dot 4** — rotate 15° clockwise
- **dots 5+6** — grow object
- **dots 2+3** — shrink object
- **dots 4+5+6** — confirm
- **dots 1+2+3** — cancel and restore

Grow/shrink accelerates the same as cursor movement. Minimum size: 10 px in smallest dimension.

### Delete on a group

- **g** — ungroup (return children to canvas)
- **c** — delete group and all contents
- **dots 1+2+3** — cancel

## New Object Menu (n)

Press **n** to open the New Object Menu. Navigate with **dot 6** / **dot 3**; confirm with **dots 4+5+6**; cancel with **dots 1+2+3**.

Shape types: **circle**, **ellipse**, **diamond**, **quadrilateral**, **triangle**, **path**. When 2+ objects are selected, **group** also appears.

### Circle

Cursor marks the center. Move to set radius. Message shows name and radius. Confirm with **dots 4+5+6**.

### Ellipse

Defined by two foci and one edge point.

**Phase 1 — set f2:** Cursor position at mode entry is f1 (fixed, marked with a cross). Move cursor to set f2. Press **dot 4** to confirm f2.

**Phase 2 — set edge:** Move cursor; the live ellipse is drawn. Press **dot 4** or **dots 4+5+6** to confirm.

**dots 1+2+3** cancels at either phase. If f1 = f2, the result is a circle.

### Quadrilateral

Cursor marks the first corner. Move to the diagonally opposite corner. Message shows name and dimensions.

### Path

Cursor marks the first vertex. Move cursor; press **dot 4** to place each vertex. When 2+ vertices exist, **dots 4+5+6** prompts "close fig? y/n" — **y** closes (polygon), **n** leaves open (polyline). **dots 1+2+3** at the prompt returns to drawing.

### Group

Available when 2+ objects are selected. Wraps selected objects into a single group.

## SVG Editor

Click **Edit SVG** in the utility bar to open the raw SVG editor. Edit the SVG source and click **Render & Send** to update the display. Click **Edit SVG** again to collapse the editor.

## Connection

Click **Connect** in the utility bar to scan for a DotPad device via Bluetooth. Requires HTTPS or localhost (Web Bluetooth secure context).

## Help

Press **?** or click the **?** button to show this help. Press **Esc** or click ✕ to close.
