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

# User Interface
When MyPaint is first opened, you'll see a single window appear with not much in
it. In the centre, there's a plain off-white paper background where you can draw.
At the top, there are toolbars and menus. At the bottom, there's a status bar with
some buttons and indicators clustered in the corners.

![First Open / In Use comparison](https://cloud.githubusercontent.com/assets/61299/12079583/60843502-b236-11e5-8ecc-36bad8507890.png)

With a bit of customization you can set up sidebars full of dockable panels and
palettes. You can make the MyPaint use the full screen area too, and tell it to
hide the controls while you're working.

For more information, see the [User Interface]({{< relref "ui" >}}) page.

# Tools
## Anatomy of a stroke
When you paint a stroke, the result is defined by different parts of MyPaint. You
can combine any _Painting Tool_, _Brush_ and _Paint Mode_ to suit your drawing style.
MyPaint uses one and the same engine for all kinds of brushes (and the eraser).

* Painting Tool: Defines how the **shape** of a stroke is made
* Brush: Defines the **look** of the stroke
* Paint Mode: Defines how the resulting color is **applied** to the canvas.


## The Painting Tools
The general painting tools change the input method of strokes and can be used to
construct geometrical shape. The lines that are created will be made with the current
brush, colour, and paint blend mode.

* [[Freehand|v1.2-Freehand-Tool]] - free drawing without constraints
* [[Inking|v1.2-Inking-Tool]] - smooth Strokes than can be modified
* Lines and Curves
* Connected Lines
* [[Ellipses and Circles|v1.2-Ellipses-and-Circles]]

### Other Tools
MyPaint also offers Tools for:
- [[Navigation|v1.2-Main-Toolbar#view-main]]
- [[canvas tools|v1.2-Main-Toolbar#core-tools]]
- the colour picker.

_Main Menu: Edit → Current Tool_

# Shortcuts for brush settings

Brush shortcut keys are used to quickly save and restore brush settings. You can
paint with one hand and change brushes with the other, even in mid-stroke.

There are 10 slots available for brushes. By default, shortcuts are assigned to
the keys `1` through `9`, and to the `0` key. To save your current brush’s settings
to one of these press `Ctrl+<number>`, for example `Ctrl+9`. To load stored settings
back, just press the number key on its own.

The brush shortcuts you assign are saved to your personal MyPaint settings, allowing
you to use them in future sessions.

By default, pressing the `Q` key saves your current brush’s settings to the most
recently used shortcut slot.

## Options
By default, brush shortcut keys remember the colour you had active when you saved
the brush.

This behaviour can be turned off using the main menu:
- _Brush → Shortcut Keys → Brush Shortcut Keys Restore Colour_.

# Preferences
![Menu - Edit - Current Tool: Overview](https://cloud.githubusercontent.com/assets/6949092/21042880/88398014-bdf4-11e6-8a51-a7ae855192f2.PNG)

The [Preferences Window]({{< relref "preferences" >}}) gives you options to configure
MyPaint's appearance, input, keyboard shortcuts and many other settings.

Open the Preferences Window by:
* Menu Edit -> Edit Preferences
* Menu Window -> Edit Preferences
