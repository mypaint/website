+++
title = "MyPaint v2.0.0-alpha Released"
author = "Brien Dieterle"
date = 2019-01-26T00:00:00Z
summary = "We have a new alpha builds, that add a bunch of new features. We would like you to download them and test them out."
tags = ["jekyll"]
+++

We have just released [mypaint v2.0.0-alpha.0](https://github.com/mypaint/mypaint/releases/).
- Spectral Paint/Pigment layer and brush mode
- Linear blending for non-pigment layers and brush modes
- Smudge enhancements
- Layer "views"
- Fullscreen improvements with autohide of toolbars
- Python3 compatibility
- A bunch of other stuff!

Please note, old files will composite layers in a linear "more correct" way. This
might look different, better, or perhaps worse. We could add legacy modes but it
is probably better to move on if possible, or render old files with an older version
of MyPaint if necessary (or even Gimp/Krita).

The pigment/paint mode is default for all brushes and new layers. If for some reason
you don't like it, or it is too slow, you can slide the "Pigment" slider to off
(from the tool options panel), and change the layer mode to Normal. This will go
back to a linear RGB blend mode (not non-linear like the old MyPaint).

Highly recommend my [brush pack](https://github.com/briend/Brushes/blob/master/Dieterle-Brushes-v4.zip) (included in AppImage, soon for Windows) 
to see many new features in action:

![PigmentMode](MyPaint-2.0-alpha.png)

special thanks to @aferrero2707 for the appimage build setup
