# DotSVG Help

## Things to Know

### Connecting the Dot Pad

Chrome seems to be best for connecting the Dot Pad via BLE. To connect the device, load the DotSVG page, turn on the Dot Pad, and press the Connect button on the web page. Tab until you find the Compatible Devices Data Grid, press down arrow, then enter.

### About the DotPad Keys

The DotPad has six keys arranged like a Perkins braille keyboard: three on the left hand (dots 1, 2, 3, from index finger outward) and three on the right hand (dots 4, 5, 6, from index finger outward). This documentation uses braille dots, letters, and chords with this keyboard configuration in mind.

### About DotSVG

This web app is a simple SVG drawing program intended to be used almost entirely from the Dot Pad itself. It uses the main 60X40 pixel display to show graphics, and the 20-cell message line below to display prompts and orientation information in uncontracted computer braille.

When the program first launches, the entire 600X400 pixel canvas is zoomed all the way out to render 100% of the canvas on the display. There are 4 objects placed by default in the 4 quadrants of the canvas. These are present just for fun and can be deleted.

The program relies on cursor movement for object placement, panning, editing, and other functions. Some functions such as device connection, object renaming, and explicit SVG code editing require interaction with the web page via screen reader, but most drawing and editing actions happen on the Dot Pad.

## The Cursor and Cursor Movement

The cursor appears on the display as a small (5 pixel) plus sign. Cursor movement accelerates: the more you press a given direction key, the faster the cursor moves. This lets you move the cursor large distances without losing your mind. Pressing any other key resets acceleration to one pixel.

- **v** — toggle cursor visibility
- **dot 3** — move left
- **dot 6** — move right
- **dot 2** — move up
- **dot 5** — move down

## Object Navigation

Using dots 1 and 4 moves the cursor among objects using an approximate top-left to bottom-right algorithm.

## Zoom & Pan

- **dots 5+6** — zoom in (halve viewport)
- **dots 2+3** — zoom out (double viewport)
- **o** — overview: full canvas with dashed viewport outline; any key returns

## Object Selection

Placing your cursor on an object is equivalent to selecting it. The name of the current object displays on the message line to confirm its identity. This is the object that will be affected when choosing object actions such as renaming or deleting. When no object is selected the message line is blank.

- **s** — toggle selection on object under cursor

## Edit Menu (e)

Press **e** to open the Edit Menu. Navigate with **dot 6** / **dot 3**; confirm with **dots 456 chord**; cancel with **dots 123 chord**.

Actions: **delete**, **rename**, **move**.

### Move mode

- **dot 3 / dot 6 / dot 2 / dot 5** — move 1 px per press
- **dot 1** — rotate 15° counter-clockwise
- **dot 4** — rotate 15° clockwise
- **dots 5+6** — grow object
- **dots 2+3** — shrink object
- **dots 456 chord** — confirm
- **dots 123 chord** — cancel and restore

Grow/shrink accelerates the same as cursor movement. Minimum size: 10 px in smallest dimension.

## New Object Menu (n)

Press **n** to place a new object at the current cursor position. Navigate options with **dot 6** / **dot 3**; select with **dots 456 chord**; cancel with **dots 123 chord**.

### New Object types:

- **Circle:** Current position marks the center. Move cursor with dots 2, 3, 5, 6 to set radius. Message shows object name and current radius (offset from center). Confirm with **dots 456 chord**; cancel with **dots 123 chord**.
- **Ellipse:** Defined by two foci and one edge point. Focus 1 is the current cursor position. Move cursor to f2 using dots 2, 3, 5, and 6, then confirm with **dot 4**. Move cursor to define a point on the edge; the ellipse adjusts in real time. Press **dot 4** or **dots 456 chord** to confirm. Press **dots 123 chord** to cancel at any time. If f1 and f2 are the same point, the result is a circle.
- **Diamond:** Placed immediately as a small diamond centered on the current cursor position. No size parameters.
- **Quadrilateral:** Cursor marks the first corner. Move to the diagonally opposite corner. Message shows name and dimensions. Confirm with **dots 456 chord**; cancel with **dots 123 chord**.
- **Triangle:** Placed immediately as a small triangle centered on the current cursor position. No size parameters.
- **Path:** Cursor marks the first vertex. Move cursor and press **dot 4** to place each subsequent vertex. When 2 or more vertices exist, **dots 456 chord** prompts "close fig? y/n" — **y** closes the shape into a polygon, **n** leaves it open as a polyline. **dots 123 chord** at the prompt returns to drawing.

## Grouping Items

Groups let you treat multiple objects as a single unit for moving, scaling, and other operations. To create a group, first select two or more objects, then use the New Object Menu.

- **s** — toggle selection on object under cursor; select 2+ objects to enable grouping
- **n** (with 2+ objects selected) — opens New Object Menu with **Group** as an additional option; confirm with **dots 456 chord** to wrap selected objects into a group
- Selected objects appear with solid fill; smaller unselected objects punch through the filled region

### Deleting a group

When the Edit Menu **delete** action is used on a group, you are given a choice of how to delete:

- **g** — ungroup: return all children to the canvas as individual objects
- **c** — delete the group and all its contents
- **dots 123 chord** — cancel

## SVG Editor

Click **Edit SVG** in the utility bar to open the raw SVG editor. Edit the SVG source and click **Render & Send** to update the display. Click **Edit SVG** again to collapse the editor.

## Connection

Click **Connect** in the utility bar to scan for a DotPad device via Bluetooth. Requires HTTPS or localhost (Web Bluetooth secure context).

## Help

Press **?** or click the **Help** button to show this help. Press **Esc** or click the **Close help** button to close.
