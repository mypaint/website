+++
title = "Footer bar"
summary = "A description of the strip of UI features at the bottom of the main window"
+++

The *Footer Bar* is the entire strip at the bottom of the [[main window|v1.2 User Interface]]. It consists of a status bar, and clusters of controls for changing the brush and colour used for painting.

* [Status bar](#status-bar)
* [Brush controls](#brush-controls)
* [Colour controls](#colour-controls)

#### Status bar

![Footer: Status Bar](https://cloud.githubusercontent.com/assets/61299/12106906/2a631340-b35c-11e5-8456-5027a4ba4257.png)

The status bar at the bottom of the main window shows the current tool, and also the canvas's zoom and rotation.

#### Colour controls

![Footer: Colour controls](https://cloud.githubusercontent.com/assets/61299/12106905/2a58820e-b35c-11e5-8e0b-f084956a6d69.png)

The colour controls are clustered into the bottom left of the footer bar. You can change the painting colour here, pick a colour off the canvas, or bookmark the current colour to the palette.

* **Eye Dropper** button _:new: Since_ MyPaint _1.2.0_
  * Lets you quickly pick a colour to paint with from the canvas.
  * The <kbd>R</kbd> key, and pressing <kbd>ALT</kbd>+<kbd>LMB</kbd> offer similar functionality.
  * Main article: [[v1.2 Pick Colour]]
* **Current and Previous Colour** indicator and menu (_Colour → Change Colour…_, or press <kbd>C</kbd>.)
  * These two coloured rectangles show the current brush colour, and the colour previously painted with.
  * Click the left-hand (current colour) swatch for a pop-up menu full of colour selectors.
  * The popup menu is the one revealed by the <kbd>C</kbd> key.
  * Click the right-hand (previous colour) swatch to revert back to that colour.
  * Main article: [[v1.2 Colour Selector Popup]]
* **Edit Colour Details** button 
  * Opens the Set Current Colour popup window
  * Change the numeric values of the current colour
  * Main article: [[v1.2 Numeric Colour values]]
* **Add Colour to Palette** button (_Colour → Add Colour to Palette_)
  * Click this to add the current brush colour to the palette.
  * The palette will open in a sidebar panel if it isn't already open.
  * Main article: [[v1.2 Palette]]

#### Brush controls

![Footer: Brush controls](https://cloud.githubusercontent.com/assets/61299/12106904/2a3a73ae-b35c-11e5-8cce-a0c8532d88ec.png)

The brush controls are clustered into the bottom right of the footer bar. You can change your brush here, or pick a brush and layer from the canvas to continue work there.

* **Current Brush** indicator and menu _(Brush → Change Brush…, or press <kbd>B</kbd>.)_
  * Shows the current brush's icon.
  * Click the icon to reveal a pop-up menu from which every brush group is available.
  * The popup menu is the one revealed by the <kbd>B</kbd> key.
  * Main article: [[v1.2 Brush groups]]
* **Pick Stroke and Layer** button
  * Allows you to pick a brushstroke from the screen.
  * If the stroke is on a different layer, _MyPaint_ will switch to that layer.
  * Invisible and locked layers (and their brushstrokes) can't be picked this way.
  * Not every kind of image has a strokemap.
  * The <kbd>W</kbd> key offers similar functionality.
  * Main article: [[v1.2 Pick Stroke and Layer]]
