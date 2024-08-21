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
When MyPaint is first opened, you'll see a single window appear with not much in it. In the centre, there's a plain
off-white paper background where you can draw. At the top, there are toolbars and menus. At the bottom, there's a status
bar with some buttons and indicators clustered in the corners.

{{< img src="mypaint-window-new.jpg" caption="A fresh installation of MyPaint" >}}

{{< img src="mypaint-window-in-use.jpg" caption="MyPaint's user interface adapts to meet your needs">}}

With a bit of customization you can set up sidebars full of dockable panels and palettes. You can make the MyPaint use
the full screen area too, and tell it to hide the controls while you're working.

## More Information
- [Main Toolbar]({{< relref "ui/main-toolbar" >}})
- [UI Toolbar]({{< relref "ui/ui-toolbar" >}})
- [Footer bar]({{< relref "ui/footer-bar" >}})
- Dockable panels
- [Fullscreen mode]({{< relref "ui/fullscreen" >}})

# Tools
## Anatomy of a stroke
When you paint a stroke, the result is defined by different parts of MyPaint. You can combine any _Painting Tool_,
_Brush_ and _Paint Mode_ to suit your drawing style. MyPaint uses one and the same engine for all kinds of brushes (and
the eraser).

* Painting Tool: Defines how the **shape** of a stroke is made
* Brush: Defines the **look** of the stroke
* Paint Mode: Defines how the resulting color is **applied** to the canvas.


## The Painting Tools
{{< img src="mypaint-preferences.jpg" caption="Menu -> Edit -> Current Tool" width="250px" float="right" >}}

The general painting tools change the input method of strokes and can be used to construct geometrical shape. The lines
that are created will be made with the current brush, colour, and paint blend mode.

* [Freehand]({{< relref "tools/freehand" >}}) - free drawing without constraints
* [Inking]({{< relref "tools/inking" >}}) - smooth Strokes than can be modified
* Lines and Curves
* Connected Lines
* [Ellipses and Circles]({{< relref "tools/ellipses-and-circles" >}})

### Other Tools
MyPaint also offers Tools for:
- [Navigation]({{< relref "ui/main-toolbar#view-main" >}})
- [Canvas tools]({{< relref "ui/main-toolbar#core-tools" >}})
- the colour picker.

# Shortcuts for brush settings
Brush shortcut keys are used to quickly save and restore brush settings. You can paint with one hand and change brushes
with the other, even in mid-stroke.

There are 10 slots available for brushes. By default, shortcuts are assigned to the keys `1` through `9`, and to the `0`
key. To save your current brush’s settings to one of these press `Ctrl+<number>`, for example `Ctrl+9`. To load stored
settings back, just press the number key on its own.

The brush shortcuts you assign are saved to your personal MyPaint settings, allowing you to use them in future sessions.

By default, pressing the `Q` key saves your current brush’s settings to the most recently used shortcut slot.

## Options
By default, brush shortcut keys remember the colour you had active when you saved the brush.

This behaviour can be turned off using the main menu:
- _Brush → Shortcut Keys → Brush Shortcut Keys Restore Colour_.

# Preferences
The [Preferences Window]({{< relref "preferences" >}}) gives you options to configure
MyPaint's appearance, input, keyboard shortcuts and many other settings.

Open the Preferences Window by:
* Menu Edit -> Edit Preferences
* Menu Window -> Edit Preferences
