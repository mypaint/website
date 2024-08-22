+++
title = "Footer bar"
summary = "A description of the strip of UI features at the bottom of the main window"
weight = 30
+++

The **Footer Bar** is a strip comprising the bottom of the [main window]({{< relref "../#user-interface" >}}). It
consists of a status bar, and two clusters of controls for changing the brush and colour.

# Status bar
{{< img src="mypaint-footer-bar-status.jpg" width="100%" >}}

The status bar at the bottom of the main window shows the current tool, and also the canvas's zoom and rotation.

# Colour controls

{{< img src="mypaint-footer-bar-colour.jpg" float="right" >}}

The colour controls are clustered on the left side of the footer bar.

**Eyedropper** button
> Press <kbd>r</kbd>, or <kbd>alt</kbd>+<kbd>lmb</kbd>
- Pick a colour from the canvas. [Read more]({{< relref "../tools/colour-picker" >}})
**Current and Previous Colour** indicator and menu
> *Colour → Change Colour…*, or <kbd>C</kbd>
- A rectangle consisting of two sides (swatches). The left swatch shows the current brush colour, the right swatch shows
the previous colour. 
- Clicking the left swatch (current colour) opens the colour selector popup. [Read more]({{< relref "../popups/colour-selector" >}})
- Clicking the right swatch (previous colour) reverts the brush to the previous colour.

**Edit Colour Details** button 
- Open the *Set Current Colour* popup window for inputting numeric colour values. [Read more]({{< relref "../colour/numeric-values" >}})

**Add Colour to Palette** button
> *Colour → Add Colour to Palette*
- Adds the current brush colour to the palette. The palette will open in a sidebar panel if it isn't already open. [Read
more]({{< relref "../panels/palette" >}})

# Brush controls
{{< img src="mypaint-footer-bar-brush.jpg" float="right" >}}

The brush controls are clustered on the right side of the footer bar.

**Current Brush** indicator and menu
> *Brush → Change Brush…*, or <kbd>B</kbd>
- A square containing the current brush icon.
- Clicking the icon opens the brush groups popup. [Read more]({{< relref "../popups/brush-groups" >}})

**Pick Stroke and Layer** button
> Press <kbd>W</kbd>
- Pick a brushstroke from the screen. If the stroke is on a different layer, MyPaint will switch to that layer.
Invisible and locked layers can't be picked. Not every kind of image has a strokemap. [Read more]({{< relref "../tools/stroke-layer-picker" >}})
