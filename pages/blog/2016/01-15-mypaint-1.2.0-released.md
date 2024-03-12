+++
title = "MyPaint 1.2.0 Released"
author = "Andrew Chadwick"
date = 2016-01-15T21:04:00Z
discourseID = 113
tags = ["jekyll"]
+++

It's been a long time since the last stable release, but I'm really happy to announce
that MyPaint version 1.2.0 is ready. Windows binaries will be available soon, and
Ubuntu packages available for testing through the usual PPA. Expect releases for
other operating systems and distros in due course.

If you'd like to build MyPaint from source yourself, you can download an official,
signed source code bundle on our [GitHub releases page][release.src].

Ubuntu PPA builds are available from the [MyPaint-testing PPA][release.ppa], and
other distributions for Linux or OS X will doubtless pick up the new release in
due course.

We expect that official Windows installers will be uploaded to the releases page
on Github soon. [Issue #564][issue.winrel] tracks the Windows build's progress for 1.2.0.

# Changes since the last stable release
- New intuitive Inking tool for smooth strokes.
- New Flood Fill tool.
- Automated backups of your working docs, with recovery on startup.
- Improved symmetry-setting and frame-setting modes.
- New workspace UI: two sidebars, with dockable tabbed panels.
- Smoother scrolling and panning.
- New brush pack.
- New brush and color history panel.
- New layer trimming command in frame options.
- Added layer groups.
- New layer modes: several masking modes added.
- Add display filters: greyscale, simulate dichromacy for trichromats.
- New color wheel options: Red/Yellow/Blue, Red-Green/Blue-Yellow.
- Uses dark theme variant by default.
- Clearer icons, prettier freehand cursors.
- Device prefs allow glitchy devices to be restricted.
- Eraser mode no longer changes the size of the brush.
- New vector layers, editable in an external app (Inkscape recommended).
- New fallback layer types: non-PNG image, data.
- More kinds of images now work as backgrounds.
- Improved Windows support
- Ported to GTK3.
- Accelerator map editor has moved to preferences.
- Many other bugfixes, translations, and code quality improvements.

[release.src]: https://github.com/mypaint/mypaint/releases/tag/v1.2.0
[release.ppa]: https://launchpad.net/~achadwick/+archive/ubuntu/mypaint-testing/+packages
[issue.winrel]: https://github.com/mypaint/mypaint/issues/564
