+++
title = "v1.2.0 User Manual"
date = 2015-01-01T12:00:00Z
summary = "Learn how to use MyPaint v1.2.0"
showTOC = true
hideSummary = true
hideList = true
[[cascade]]
sectionNavURL = "/docs/manuals/v1.2.0"
+++

Welcome to the MyPaint v1.2.0 User manual. Here you can learn the broad strokes of how MyPaint works.

# User Interface
When MyPaint is first opened, a single relatively sparse window will appear. At the centre, there's a plain off-white
background where you can draw (the **canvas**). At the top, there are toolbars and menus. At the bottom, there's a
status bar with some buttons and indicators clustered in the corners.

{{< img src="mypaint-window-new.jpg" caption="A fresh installation of MyPaint" >}}
<br>
{{< img src="mypaint-window-in-use.jpg" caption="MyPaint can be customised with dockable panels and palettes, all hideable while you work.">}}

<br>

{{< flex grow="true" >}}
    {{< bigbutton title="Main Toolbar" subtitle="Painting tools and other commands" href="ui/main-toolbar" >}}
    {{< bigbutton title="UI Toolbar" subtitle="Customise the user interface" href="ui/ui-toolbar" >}}
    {{< bigbutton title="Footer Bar" subtitle="Application status and brush controls" href="ui/footer-bar" >}}
    {{< bigbutton title="Dockable Panels" subtitle="Tailor your painting experience" href="./panels-popups" >}}
    {{< bigbutton title="Fullscreen Mode" subtitle="Maximise drawing space" href="ui/fullscreen" >}}
{{< /flex >}}

# Painting
When brush strokes are placed on the canvas, three elements determine the change made to the picture: The *painting
tool*, *brush*, and *paint mode*. These three elements can be combined arbitrarily to fit any desired art style.

1. **Painting Tool**: Determines the broad *geometry* of the stroke.
2. **Brush**: Determines the *design* of the stroke.
3. **Paint Mode**: Determines the *effect* of the stroke unto the canvas.


## Painting Tools
> *Menu → Edit → Current Tool*

Painting tools change how the user makes strokes by adding or removing contraints on stroke input.

{{< flex grow=true >}}
    {{< bigbutton title="Freehand" subtitle="Unconstrained strokes" href="painting/freehand" >}}
    {{< bigbutton title="Lines & Curves" subtitle="Singular constrained strokes" href="painting/lines-and-curves" >}}
    {{< bigbutton title="Connected Lines" subtitle="Consecutive lines & curves" href="painting/connected-lines" >}}
    {{< bigbutton title="Ellipses & Circles" subtitle="Constrained circular strokes" href="painting/ellipses-and-circles" >}}
    {{< bigbutton title="Inking" subtitle="Modify a stroke before committing to it" href="painting/inking" >}}
{{< /flex >}}

## Brushes
[Read more]({{< relref "./painting/brushes" >}})

## Paint Modes
blend modes, eraser. [Read more]({{< relref "painting/paint-modes" >}})

# Canvas Tools
Tools also exist to interact with the canvas in other ways.

{{< flex grow=true >}}
    {{< bigbutton title="View Tools" subtitle="Modify the viewport" href="ui/main-toolbar#view-main" >}}
    {{< bigbutton title="Reposition Layer" subtitle="Modify a layer's position" href="canvas-tools/reposition-layer" >}}
    {{< bigbutton title="Flood Fill" subtitle="Fill an enclosed area with colour" href="canvas-tools/flood-fill" >}}
    {{< bigbutton title="Colour Picker" subtitle="Pick a brush colour from the canvas" href="canvas-tools/colour-picker" >}}
    {{< bigbutton title="Stroke/Layer Picker" subtitle="Pick a brush stroke from the canvas" href="canvas-tools/stroke-layer-picker" >}}
    {{< bigbutton title="Symmetry" subtitle="Add lines of symmetry brush strokes" href="canvas-tools/symmetry" >}}
    {{< bigbutton title="Edit Frame" subtitle="Set a working space in the canvas" href="canvas-tools/frame" >}}
{{< /flex >}}

# Preferences
> *Edit → Edit Preferences*, or *Window → Edit Preferences*

The preferences window gives you options to configure MyPaint's appearance, input, keyboard shortcuts and many other
settings. [Read more]({{< relref "preferences" >}})
