+++
title = "Concepts"
date = 2011-01-01T12:00:00Z
summary = "Concepts for MyPaint v0.9.0"
+++

MyPaint has a very simple model of how painting works. This page is intended to
describe that model and the concepts involved, so that users can understand it.
If you are looking for implementation details or is interested in using the MyPaint
brush engine in your own application, see [this page]({{< relref "/docs/backend/brush-engine" >}}).

The following information may not be complete.

# Basics
Painting is done with a *brush*, MyPaint's only tool for use on the canvas. Painting
with the brush is done by brush *strokes*. Basically, a brush stroke starts when
you move the cursor with pressure using a [pen tablet](http://en.wikipedia.org/wiki/Graphics_tablet)
(or by pressing and holding a mouse button) and finishes when you release the pressure/button.
Multiple brush strokes are used to *paint* an image on MyPaint's virtual canvas.
This image can be saved for sharing at any time. The goal of MyPaint is to be a
simple and powerful program for digital artists to paint in a natural way.

# Brushes

{{< img src="BrushStroke003.png" width="20em" float="right"
caption="A circular brush stroke with the individual dabs visible" >}}

But what is a brush stroke really? In MyPaint, a brush stroke consists of a number
of *dabs*.

## Dabs
A dab is simply a circle or ellipse with a certain position, size, direction, color,
and opacity. Try zooming in very close and test out different brushes, like `basic`
or `long\_grass`. Move the brush slowly, and you can actually see the different dabs
that make up a stroke! Note that for many brushes the individual dabs are very often
overlapping, so that the stroke ends up more or less continuous.

## Brush types
Brushes come in many different types. There are pencil brushes, pastel brushes,
airbrushes, and of course, paintbrushes. Different brushes respond differently to
tablet input. Some respond only to pressure. Some respond to tilt. Others respond
to speed, direction, or even to what's already on the canvas. Different brushes
can have wildly different effects. Make sure to try many to find the ones you enjoy
using the most.

## Eraser
There is a special brush function that removes from the canvas instead of adding
to it: this is the *eraser*. It achieves a similar goal as you would expect a real
eraser to. Some brushes default to eraser mode when you select them, but all brushes
can be used as erasers. Just push the *e* key to toggle between normal and eraser
brush modes.

## Brush settings
{{< img src="BrushSettings.png" float="right" width="20em"
caption="The Brush Settings dialog showing some settings for the \"bulk\" brush." >}}

So, what makes `charcoal` look different from say, `Ico_Line_Dropping`? What separates
them are their *brush settings*, which decide how all these dabs look and are distributed.
This is what you are seeing when you open the "brush settings" dialog. So all brushes
are actually just variants of the same basic brush.

The "brush settings" dialog can be opened from the program menu, or by pressing
the keyboard combination *CTRL+B*. A simple tutorial can be found [here](http://mypaint.intilinux.com/?page_id=173).
More in-depth information can be found in [User Manual v0.9.0]({{< relref "../" >}}).

## Stroke properties
Now you may ask, how could this ever look and feel somewhat like a real "ink" or
"watercolor" brush? One key feature in this aspect is that the look and position
of dabs (and thus the entire stroke) can depend on how you move the brush.

It can depend on things like how fast you move, the direction of the stroke and/or
the pressure you apply. Different pen tablets can give you different additional
functions. Some include tilt, rotation, more precise pressure, and even automatic
digital brush switching between different physical pens.

## Brush groups
Brushes are sorted into groups. You can move brushes between groups, and make your
own from the Brush Selection dialog.

Imported brushes usually come pre-sorted into their own group.

You can add new brush packs by importing them. See [Brush Packages]({{< ref "../brush-packages" >}})
for details.

# Canvas
MyPaint uses an essentially infinite canvas to paint on. You will never run out
of room as long as your computer can handle the amount of data.

{{< img src="view-menu.png" float="right" caption="MyPaint's view menu" >}}

MyPaint's saving automatically picks a size just big enough to contain all of your
painting. Unless you make a very large image, you don't have to worry about accidentally
saving impossibly large files. Only the part of the canvas you are using is saved.

## View Options
Your view of the canvas can be rotated, enlarged, shrunk, mirrored vertically or
horizontally, and made fullscreen.

None of these make any changes to the image itself, only how you see it. There are
many benefits to this. For example, rotating the canvas allows you to more comfortably
and naturally sketch without needing to strain your hand to get the right angle.
Mirroring the canvas is another important technique. It allows you to easily spot
mistakes and weird lines by showing you the image in a different way.

## Background
{{< img src="background.png" float="right" width="30em" >}}

MyPaint allows changing how the canvas looks and setting a default for all new images.
The *background* can be made to resemble many different types of media you might
draw or paint on, including notebook paper, graph paper, or painting canvas. These
can be set for aesthetic reasons, to reduce glare, or to help you better see transparent
spots in your artwork.

There are many backgrounds to choose from, and adding your own is a simple as placing
a 64x64 pixel image in MyPaint's "backgrounds" folder. These square images are repeated
infinitely in all directions, giving you an infinite canvas that's generated as you need it.


# Misc
Like most programs, MyPaint has Undo and Redo functions. MyPaint, however, only
undoes the most recent brush strokes. Brush strokes made in quick succession will
count as a single group when undoing or redoing.

