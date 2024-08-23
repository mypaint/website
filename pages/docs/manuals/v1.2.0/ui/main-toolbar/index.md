+++
title = "Main Toolbar"
summary = "The main toolbar contains painting tools and other commands"
hideSummary = true
weight = 10
+++

{{< id "main-toolbar-image" nomd >}}
{{< img src="main-toolbar.jpg" caption="The main toolbar with the context menu open" >}}
{{< /id >}}

The **Main Toolbar** contains MyPaint's painting tools, and other commands. It is located at the top of the
[main window]({{< relref "../#user-interface" >}}), underneath the menubar. It continues into the [UI toolbar]({{< relref
"ui-toolbar" >}}).

Clicking on a blank area of the main toolbar with the right mouse button reveals a context menu used to show/hide
buttons

# File Handling
{{< img src="main-toolbar-file.jpg" float="right" >}}
The File Handling toolbar buttons let you load and save the working canvas. They are visible by default.

**New File**
> *File → New*, or <kbd>Ctrl</kbd>+<kbd>N</kbd>
- Starts a new, blank canvas.

**Open File**
> *File → Open…*, or <kbd>Ctrl</kbd>+<kbd>O</kbd>
- Open a file on disk, so it can be edited in the canvas area.

**Save File**
> *File → Save…*, or <kbd>Ctrl</kbd>+<kbd>S</kbd>
- Saves the current canvas to a file on disk. If it hasn't got a file name yet, you'll be asked for one.

# Core Tools
{{< img src="main-toolbar-tools.jpg" float="right" >}}

The core set of tools cannot be hidden using the popup menu.

**Eraser**
> *Brush → Paint Mode → Paint Mode: Eraser*, or <kbd>E</kbd>

- Toggles the Eraser paint/blend mode, which affects how the painting tools operate. [Read more]({{< relref
"../painting/paint-modes#eraser" >}})
- Other optional paint modes can be toggled on the toolbar, see [blend modes]({{< relref "#blend-modes" >}}).


**Freehand** (paintbrush)
> *Edit → Freehand*, or <kbd>P</kbd>

- The default painting tool; paint using the current brush and colour, without constraints. [Read more]({{< relref
"../painting/freehand" >}})

**Pick Colour** (eyedropper)
> *Colour → Pick Colour*, or <kbd>R</kbd>

- Pick a new painting colour from the canvas. [Read more]({{< relref "../canvas-tools/colour-picker" >}})

**Flood Fill** (paint bucket)
> *Edit → Flood Fill*

- Fills an area with the current painting colour.

**Reposition Layer**
> *Layer → Reposition Layer*

- Move the current layer relative to all the other layers.

**Edit Frame** (picture frame)
- MyPaint's canvas is infinite, the edit frame tool defines a rectangular canvas area for exports etc.

**Edit Painting Symmetry** (butterfly)
> *Edit → Edit Painting Symmetry*

- Define an axis for painting symmetrically. Symmetry mode affects all normal painting tools.

# Scraps Switcher
{{< img src="main-toolbar-scraps.jpg" float="right" >}}

The Scraps Switcher toolbar buttons let you quickly save drafts to a dedicated folder on disk, and load them in again.
These items are optional, you need to use the [main toolbar's context menu]({{< relref "#main-toolbar-image" >}}) to
make them visible.

Scrap file revisions are stored with numbered filenames in a single folder. The scrap folder's location can be changed
in the [Preferences window]({{< relref "../preferences" >}})

**Save As Scrap**
> *File → Save As Scrap*, or <kbd>F2</kbd>
- Saves the working canvas to a scrap file. This changes the filename, so _File → Save_ will write over the new scrap.
- If the file is _already_ a scrap file, a new _revision_ is saved.

**Open Previous Scrap**
> *File → Open Previous Scrap*, or <kbd>F6</kbd>
- Loads the scrap file before the current one.
- If your working file isn't a scrap file, you'll get the last scrap file in your scrap folder.
- If the scrap file has revisions, this will load only the latest revision.

**Open Next Scrap**
> *File → Open Next Scrap*, or <kbd>F7</kbd>
 - This works just like Open Previous Scrap, but in the opposite direction.

# Undo and Redo
{{< img src="main-toolbar-undo-redo.jpg" float="right" >}}

These are the normal undo and redo controls. The only difference between these and their equivalents from other apps is
that MyPaint's freehand mode uses shortish fragments of continuous painting as its undo step.

The toolbar items are only sensitive when you can undo or redo a step.

**Undo**
> *Edit → Undo \<action\>*, or <kbd>Ctrl</kbd>+<kbd>Z</kbd>, or <kbd>Z</kbd>

**Redo**
> *Edit → Redo \<action\>*, or <kbd>Ctrl</kbd>+<kbd>Y</kbd>, or <kbd>Y</kbd>


# Blend Modes
{{< img src="main-toolbar-blend.jpg" float="right" >}}

Paint blend modes change how your brush affects the layer you paint on. These toolbar buttons are optional, and you need
to use the [main toolbar's context menu]({{< relref "#main-toolbar-image" >}}) to make them visible. [Read more about
paint modes]({{< relref "../painting/paint-modes" >}})

**Lock Alpha** (padlock)
> *Brush → Paint Mode → Paint Mode: Lock Alpha*, or <kbd>Shift</kbd>+<kbd>L</kbd>
- Applying the brush doesn't change the transparency of the pixels you paint over (in the target layer). Use this for
further highlighting or shading objects that are painted on their own layer. [Read more]({{< relref
"../painting/paint-modes#lock-alpha" >}})
- It's analogous to painting on layer groups which contain a mask, but a lot less fiddly.

**Colourize** (rainbow)
> *Brush → Paint Mode → Paint Mode: Colourize*, or <kbd>Shift</kbd>+<kbd>K</kbd>
- Painting applies the _hue_ (kind of colour) and _saturation_ (degree of colour) of your brush to whatever you paint on.
The _value_ (brightness or darkness) of what you paint on isn't affected. [Read more]({{< relref
"../painting/paint-modes#colourize" >}})
- This paint mode also doesn't change the transparency of what you paint on.
- Use this for adjusting colours, or _assigning_ colour to something you've painted in greyscale.


# Line Modes
{{< img src="main-toolbar-lines.jpg" float="right" >}}

These tools let you draw geometric shapes. The lines that are created will be made with the current brush, colour, and
paint blend mode.

**Lines and Curves**
> *Edit → Lines and Curves*, or <kbd>K</kbd>
- Draw straight lines, hold down <kbd>Ctrl</kbd> to constrain the angle. [Read more]({{< relref "../painting/lines-and-curves" >}})
- When this tool is active, you can add curves to the last straight line you drew by pressing <kbd>Shift</kbd> and dragging.
- You can add up to two bends in each straight line.

**Connected Lines**
> *Edit → Connected Lines*, or <kbd>J</kbd>
- Draw a line from where you last painted. Constraints and curving work just like the Lines and Curves tool. [Read
more]({{< relref "../painting/connected-lines" >}})

**Ellipses and Circles**
> *Edit → Ellipses and Circles*, or <kbd>O</kbd>
- Draw circles and ellipses (stretched-out circles). [Read more]({{< relref "../painting/ellipses-and-circles" >}})
- Holding down <kbd>Shift</kbd> allows you to change the angle of an ellipse.
- Holding down <kbd>Ctrl</kbd> constrains the aspect ratio (how stretched-out it looks).
- When you hold down <kbd>Ctrl</kbd>+<kbd>Shift</kbd> together, the angle is constrained instead.

**Inking**
> *Edit → Inking*
 - Draw smooth strokes with your stylus or mouse. [Read more]({{< relref "../painting/inking" >}})

# Navigation
## View (Main)
{{< img src="main-toolbar-view.jpg" float="right" >}}

These items allow you to adjust the viewport by clicking and dragging on the canvas. They are standard view manipulation
tools, so they are visible by default.

**Pan View**
> *View → Pan View*
- Move the view horizontally or vertically across the canvas.

**Zoom View**
> *View → Zoom View*
- Zoom the view in to the canvas (for detailed work) or zoom out (for an overview).

**Rotate View**
> *View → Rotate View*
- Tilt/turn the canvas within the viewport.

- **Mirror Horizontal**
> *View → Adjust View → Mirror Horizontal*, or <kbd>I</kbd>
- Flip the current view from left to right.
- This allows you to ensure your sketches look right from both directions.

## View (Alternative/Secondary)
{{< img src="main-toolbar-view-alt.jpg" float="right" >}}

These buttons allow single-click adjustments of the view. These items are optional, you need to use the [main toolbar's
context menu]({{< relref "#main-toolbar-image" >}}) to make them visible.

There's no equivalent of these buttons for the canvas position, but the cursor keys will pan around the canvas.

**Zoom In** and **Zoom Out**
> *View → Adjust View*, or <kbd>-</kbd> or <kbd>,</kbd> to zoom out, or <kbd>+</kbd> or <kbd>.</kbd> to zoom in
- Change the canvas magnification by one step.

**Rotate Counterclockwise** and **Rotate Clockwise**
> *View → Adjust View*, or <kbd>Ctrl</kbd>+<kbd>Left</kbd> or <kbd>Ctrl</kbd>+<kbd>Right</kbd>
- Change the canvas rotation by one angular step.

## View (Resetting)
{{< img src="main-toolbar-view-reset.jpg" float="right" >}}

These are for resetting the view. These items are optional, you need to use the [main toolbar's context menu]({{< relref
"#main-toolbar-image" >}}) to make them visible.

**Reset and Centre View**
> *View → Reset and Centre View*, or <kbd>F12</kbd>
- Resets the view fully, discarding any rotation, mirroring, or position.

**Fit to View**
> *View → Fit to View*, or <kbd>F10</kbd>
- The view is toggled between a fitted view, and an overview of your whole canvas.
- The fitted view retains your mirroring and rotation settings.
- Adjusting the view while it's fitted to your work discards your old saved zoom and position.
- This can be used for selecting a new area to work on, or for bouncing between a quick overview and what you're
currently focussing on.
