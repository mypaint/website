+++
title = "Main Toolbar"
summary = "The main toolbar contains painting tools and other commands"
hideSummary = true
+++

![Toolbar Customization Menu](https://cloud.githubusercontent.com/assets/61299/12079673/5da4837a-b239-11e5-977a-c07ec958f17f.png)

The **Main Toolbar** contains MyPaint's painting tools, and other commands. It is located at the top of the [[main window|v1.2 User Interface#main-window]], next to the menu. It continues into the [[UI toolbar|v1.2 UI Toolbar]]. Clicking on a blank area of the main toolbar with the right mouse button shows a popup menu which you can use to tailor what appears on it.

### Contents

* [File Handling](#file-handling)
* [Scraps Switcher](#scraps-switcher)
* [Undo and Redo](#undo-and-redo)
* [Blend Modes](#blend-modes)
* [Line Modes](#line-modes)
* [View (Main)](#view-main)
* [View (Alternative/Secondary)](#view-alternativesecondary)
* [View (Resetting)](#view-resetting)

### File Handling

The File Handling toolbar buttons let you load and save the working canvas. They are visible by default.

![Toolbar: File handling](https://cloud.githubusercontent.com/assets/61299/12079693/45e5e3c2-b23a-11e5-9cc2-a8ba18e2ac78.png)

* **New File** (_File → New_, or `Ctrl+N`). Starts a new, blank canvas.
* **Open File** (_File → Open…_, or `Ctrl+O`). Open a file on disk, so it can be edited in the canvas area.
* **Save File** (_File → Save…_, or `Ctrl+S`). Saves the current canvas to a file on disk. If it hasn't got a file name yet, you'll be asked for one.

### Core Tools

![Toolbar: Core Tools](https://cloud.githubusercontent.com/assets/61299/12079833/6e643ae2-b23f-11e5-9427-34f209270ba9.png)

The core set of tools cannot be hidden using the popup menu.

* **Eraser** (_Brush → Paint Mode → Paint Mode: Eraser_, or `E`)
  * Toggles the Eraser paint/blend mode.
  * This is a toggle which affects how the painting tools operate.
  * Main article: [[v1.2 Paint-Modes: Eraser|v1.2-Paint-Modes#eraser]]
  * Other optional paint modes can be toggled on the toolbar: see [Blend Modes](#blend-modes) below.
* **Freehand (paint brush)** (_Edit → Freehand_, or `P`)
  * Paint using the current brush and colour, without constraints.
  * This is the default painting tool.
  * Main article: [[v1.2 Freehand Tool]]
* **Pick Colour (eye dropper)** (_Colour → Pick Colour_, or `R`)
  * Pick a new painting colour from the canvas.
  * This may be moved to the footer bar in future versions of MyPaint.
  * Main article: [[v1.2 Pick Colour]]
* **Flood fill (paint bucket)** (_Edit → Flood Fill_) _:new: Since MyPaint 1.2.0_
  * Fills an area with the current painting colour.
* **Reposition Layer** (_Layer → Reposition Layer_)
  * Move the current layer relative to all the other layers.
* **Edit Frame (picture frame)** (FIXME: no simple menu item!) _:new: Since MyPaint 1.2.0_
  * Defines a rectangular canvas area for exports etc.
  * MyPaint's canvas is infinite: this allows you define a scope.
* **Edit Painting Symmetry (butterfly)** (_Edit → Edit Painting Symmetry_) _:new: Since MyPaint 1.2.0_
  * Define an axis for painting symmetrically.
  * Symmetry mode affects all normal painting tools.

### Scraps Switcher

![Toolbar: Scraps Switcher](https://cloud.githubusercontent.com/assets/61299/12079710/77feed9e-b23b-11e5-8242-4142514698c0.png)

The Scraps Switcher toolbar buttons let you quickly save drafts to a dedicated folder on disk, and load them in again. These items are optional, you need to use the [main toolbar's context menu](#appearance) to make them visible.

* **Save As Scrap** (_File → Save As Scrap_, or `F2`). Saves the working canvas to a scrap file.
  * This changes the filename, so _File → Save_ will write over the new scrap.
  * If the file is _already_ a scrap file, a new _revision_ is saved.
* **Open Previous Scrap** (_File → Open Previous Scrap_, or `F6`). Loads the scrap file before the current one.
  * If your working file isn't a scrap file, you'll get the last scrap file in your scrap folder.
  * If the scrap file has revisions, this will load only the latest revision.
* **Open Next Scrap** (_File → Open Next Scrap_, or `F7`).
  * This works just like Open Previous Scrap, but in the opposite direction.

Scrap file revisions are stored with numbered filenames in a single folder. The scrap folder's location can be changed in the [[Preferences window|v1.2 Preferences]].

### Undo and Redo

![Toolbar: Undo and Redo](https://cloud.githubusercontent.com/assets/61299/12079995/7e56b970-b244-11e5-859c-2265f6c1ac8d.png)

These are the normal undo and redo controls. The only difference between these and their equivalents from other apps is that MyPaint's freehand mode uses shortish fragments of continuous painting as its undo step.

* **Undo** (_Edit → Undo \<action\>_, or `Ctrl+Z`, or `Z`)
* **Redo** (_Edit → Redo \<action\>_, or `Ctrl+Y`, or `Y`)

The toolbar items are only sensitive when you can undo or redo a step.

### Blend Modes

![Toolbar: Paint blend modes](https://cloud.githubusercontent.com/assets/61299/12079975/f0bf5ffe-b243-11e5-8a72-5057ca4004c7.png)

These are additional paint blend modes. These toolbar buttons are optional. You need to use the [main toolbar's context menu](#appearance) to make them visible.

* **Lock Alpha (padlock)** (_Brush → Paint Mode → Paint Mode: Lock Alpha_, or press `Shift+L`)
  - Applying the brush doesn't change the transparency of the pixels you paint over (in the target layer).
  - Use this for further highlighting or shading objects that are painted on their own layer.
  - It's analogous to painting on layer groups which contain a mask, but a lot less fiddly.
  - Main article: [[v1.2 Paint Modes: Lock Alpha|v1.2 Paint Modes#lock alpha]]
* **Colourize (rainbow)** (_Brush → Paint Mode → Paint Mode: Colourize_, or press `Shift+K`)
  - Painting applies the _hue_ (kind of colour) and _saturation_ (degree of colour) of your brush to whatever you paint on.
  - The _value_ (brightness or darkness) of what you paint on isn't affected.
  - This paint mode also doesn't change the transparency of what you paint on.
  - Use this for adjusting colours, or _assigning_ colour to something you've painted in greyscale.
  - Main article: [[v1.2 Paint Modes: Colourize|v1.2 Paint Modes#colourize]]

Paint blend modes change how your brush affects the layer you paint on. See [[v1.2 Paint Modes]] for the full list.

### Line Modes

![Toolbar: Line modes](https://cloud.githubusercontent.com/assets/61299/12079974/f0b722f8-b243-11e5-83f9-371a1d464477.png)

These tools let you draw geometric shapes. The lines that are created will be made with the current brush, colour, and paint blend mode.

* **Lines and Curves** (_Edit → Lines and Curves_, or press `K`)
  * Draw straight lines, hold down `Ctrl` to constrain the angle.
  * When this tool is active, you can add curves to the last straight line you drew by pressing `Shift` and dragging.
  * You can add up to two bends in each straight line.
  * Main article: [[v1.2 Lines and Curves]]
* **Connected Lines** (_Edit → Connected Lines_, or press `J`)
  * Draw a line from where you last painted.
  * Constraints and curving work just like the Lines and Curves tool.
  * Main article: [[v1.2 Connected Lines]]
* **Ellipses and Circles** (_Edit → Ellipses and Circles_, or press `O`)
  * Draw circles and ellipses (stretched-out circles).
  * Holding down `Shift` allows you to change the angle of an ellipse.
  * Holding down `Ctrl` constrains the aspect ratio (how stretched-out it looks).
  * When you hold down `Ctrl+Shift` together, the angle is constrained instead.
  * Main article: [[v1.2 Ellipses and Circles]]
* **Inking** (_Edit → Inking_) _:new: Since MyPaint 1.2.0_
  * Draw smooth strokes with your stylus or mouse.
  * Main article: [[v1.2 Inking Tool]].

## Navigation

### View (Main)

![Toolbar: View (Main)](https://cloud.githubusercontent.com/assets/61299/12080099/730a46aa-b248-11e5-9a86-d7da7c1387c6.png)

These items allow you to adjust the viewport by clicking and dragging on the canvas. They are standard view manipulation tools, so they are visible by default.

* **Pan View** (_View → Pan View_)
  * Move the view horizontally or vertically across the canvas.
* **Zoom View** (_View → Zoom View_)
  * Zoom the view in to the canvas (for detailed work) or zoom out (for an overview).
* **Rotate View** (_View → Rotate View_)
  * Tilt/turn the canvas within the viewport.
* **Mirror Horizontal** (_View → Adjust View → Mirror Horizontal_, or press `I`)
  * Flip the current view from left to right.
  * This allows you to ensure your sketches look right from both directions.

### View (Alternative/Secondary)

![Toolbar: View (Alternative/Secondary)](https://cloud.githubusercontent.com/assets/61299/12264171/b784beb0-b92c-11e5-8459-226f34edb91d.png)

These buttons allow single-click adjustments of the view. These items are optional, you need to use the [main toolbar's context menu](#appearance) to make them visible.

* **Zoom In** and **Zoom Out** (in _View → Adjust View_, or press `-` or `,` to zoom out, or `+` or `.` to zoom in)
  * Change the canvas magnification by one step.
* **Rotate Counterclockwise** and **Rotate Clockwise** (in _View → Adjust View_, or press `Ctrl+Left` or `Ctrl+Right)
  * Change the canvas rotation by one angular step.

There's no equivalent of these buttons for the canvas position, but the cursor keys will pan around the canvas.

### View (Resetting)

![Toolbar: View (Resetting)](https://cloud.githubusercontent.com/assets/61299/12080097/72dff40e-b248-11e5-9b18-cecc3ddc5836.png)

These are for resetting the view. These items are optional, you need to use the [main toolbar's context menu](#appearance) to make them visible.

* **Reset and Centre View** (_View → Reset and Centre View_, or press `F12`)
  * Resets the view fully, discarding any rotation, mirroring, or position.
* **Fit to View** (_View → Fit to View_, `F10`)
  * The view is toggled between a fitted view, and an overview of your whole canvas.
  * The fitted view retains your mirroring and rotation settings.
  * Adjusting the view while it's fitted to your work discards your old saved zoom and position.
  * This can be used for selecting a new area to work on, or for bouncing between a quick overview and what you're currently focussing on.
