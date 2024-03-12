+++
title = "v0.7.0 User Manual"
date = 2009-08-04T12:00:00Z
summary = "Learn how to use MyPaint v0.7.0"
author = "Martin Renold, Griatch"
hideList = true
+++

Here I want to explain you how I use my program. My goal for MyPaint was “scribble
without thinking”. I want as little distraction as possible from the painting process.
If you are drawing with the mouse you might notice small problems between the strokes.
MyPaint is not really optimized for the mouse. If you paint often I really recommend
a graphic tablet.

# General
MyPaint can save/load .ora (OpenRaster format, default and working format, keep
layers), .png (with and without alpha) and jpg. You can use the GIMP for final touch
up, cropping and all the “manipulation” stuff. I paint with my left hand on the
left half of the keyboard. That’s how the shortcuts are arranged, but you can easily
change them.

# Brush Size
{{< img src="ResizingBrush.png" width="8em" float="right" >}}

To increase the size of the brush, press the F key. Press the D key to make it smaller.
Try to use those keys instinctively. You can use them in the middle of a stroke.
However some brushes, especially the first two, change their size with your movement
speed. Changing their radius will not work very well (because the speed is measured
relative to the current radius). You control the size of those brushes by moving
faster or slower. This works best when painting with small successive movements
instead of doing one straight stroke.

# Change the Color
{{< img src="ColourChooser.png" width="12em" float="left" >}}

Press the G key to open the GTK color dialog. Choose your color. Press G again to
get rid of it. Scribble around a bit with your new color, then press V. The color
at the center is your current color. The horizontal stripe changes the brightness
only, the vertical one saturation only. The colors around will look different every
time. This is a very fast way to get shades of one color. I prefer it over the GTK
dialog except for the very dark shades. It is hard to distinguish those dark colors
from each other before they cover a big area.

Finally, point at your painting and press the R key. This picks the color at the
cursor – no mouse click is needed. This is even faster, but you get no color variation.

# Unlimited Canvas
The border of the screen is not the end. The canvas is always a little bit bigger
than this and will grow when you resize the window or move around. In the View menu,
read the Help text now. You can zoom in and out using the + and - keys. The thing
to remember is that zooming out can be dangerous. You will probably notice a heavy
slowdown before you run out of memory. Anyway, try it while you have nothing to lose.

# Modify Last Stroke
If you want to experiment with the color of a stroke you can hit M to start modifying
the last stroke. Nothing will happen until you change the brush (usually color,
opacity or size). I like this when drawing clouds or fog or, in general, faint strokes
that cover a large area. You can press M again to include earlier strokes. Press
N or simply start to paint to get out of this mode. (demo)

# The Brush Dialog
{{< img src="BrushList.png" float="right" >}}

Open the edit expander in the brush dialog. The white space at the bottom of the
graphical brush list is for trying out your brush. Use it a bit. You can drag the
brushes around in the list to reorder them. On startup the upper left brush will
be selected. Now choose the reddish brush at the top (the image looks a bit different
in 0.5.0). Click on it once more to show the bigger preview image. Try it a bit,
I think it is a good one.

The first thing to note is that it gets more randomness when you increase pressure.
And it will grow when you move around faster. And the brightness changes. You have
to get a feeling for this brush before you can use it productively. Especially,
try what happens when you move very slow and press very hard. (On this image the
size was never changed.)

# Brushes
## Create your own brush
The rest of this tutorial is about making and changing brushes. Let’s say you like
this brush, but not the fact that the brightness gets changed. Open the brush settings
window from the Dialogs menu. So many settings! I have to admit that I don’t remember
what some of them do myself. Look at the tooltip info for color brightness at the
bottom. A text will appear when your mouse rests over the label. That must be it!
But why is it at zero? Well what you see here is the base value, independent of
speed, pressure, whatever. Change it until it shows 2.0. Change your Color to black
and draw a bit.

{{< img src="Customize-Your-Brush.jpg" float="right" >}}

OK, that was a bad idea, and it still does change with speed! Click on the red brush
again to restore the original settings. Click on the X button right to the change
color value (HSV) slider. The X indicates that something interesting was changed
here, in contrast to the buttons labeled with … three dots.

Move the by random slider to the maximum, just for fun, and try your brush. You
could increase the base value a bit to make the brush brighter on average. But now
press all the zero buttons to get rid of this stuff completely. Try it, it did actually work.

There is no need to alter the curve you see at by random because its y-range now
goes from zero to zero. This curve will not be saved any more with your brush because
it has no effect.

An useful helper when creating brushes is Modify Last Stroke from the Edit menu. (demo)

## Save your new brush
Easy. In the brush dialog, click on add as new. Your new brush is at the upper left
corner (remember, you can drag it around). But it needs a different image! Press
clear and draw something that both shows your brush and is easy to recognize. Then
press save preview. If you improve the brush settings even more, remember to save
settings before you switch to another brush or quit.

It is also possible to draw the preview image with a different brush. Remember:
click once to load the brush settings, click again to load its image. You can also
change the preview (actually the settings file too) with an external program. MyPaint
will notice the changes when you select the brush again. Maybe you want our GIMP
template for the labels.

## Share your brush
This goes manually, sorry about that. Look at the directory `~/.mypaint/brushes/`,
use the png images to find the number of your brush. You can rename those files,
as long as you keep the .myb extension MyPaint will find them. The file `b???.myb`
is most important, but you better get the `_prev.png` too for a nice preview. Wow,
somebody is actually reading all this stuff! Well, if you ever come up with an own
brush (or a whole collection) that you like and use often, please drop me an email
so I can include it into the next release.

# Version history
[Source page (Archived)](https://web.archive.org/web/20090426235208/http://mypaint.intilinux.com:80/?page_id=3)
    - The archived page is not necessarily the version shown here (in fact, the
site shows the latest release at that date to be v0.6.0)

## 2009-08 
> Originally written solely by Martin Renold, then updated and revised by Griatch
in autumn of 2009 to cover the 0.7 version.
- Unknown

## 2009-08-04T21:13:00:00Z
> Originally I copied this here to facilitate collaborative editing and improvement
but on second thought I'm not sure this really is suitable for being edited/improved
by many, due to the personal style and tone of the tutorial. But there are things
(most notably new features like layers) we should document for users. Feel free
to discuss how this is best done here!

Jonnor 21:13, 4 August 2009 (UTC)

> Edit this if you want, but it's probably just as easy to start from scratch.

maxy (testing anonymous wiki edits)

## 2015-03-08
> I've ported this to the new wiki, since the design notes and ethos should be kept
relevant even if the page is a bit outdated for users

achadwick, 8 Mar 2015.

## 2024-01-19
> Ported over from the GitHub wiki. If you're reading this in another 15 years, find me and come say hello!

Aesara Binder, 19 January 2024
