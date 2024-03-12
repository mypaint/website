MyPaint is considering moving to a linear light workflow internally:
this has significant artistic and aesthetic benefits for users.
We'll attempt to retain backwards compatibility for older images
to reduce the impact of this change as much as possible.

## Benefits of linear light

Linear light composition affects the way mid-range alpha pixels combine
with the layers below them.  You might see less fringing at the edges of
brushstokes, and should see fewer artefacts around the edges of strokes
when scaling.  More difficult to spot are the effects when compositing
one layer over another and altering the opacity of the top layer.
changes to the opacity slider should result in brightness changes in a
way that's no longer proportional to the way the human eye responds:
instead it's proprtional to the way light combines.

The results of a 'crossfade' done in such a way are said to be "more
cinematic", "grey out" highlights less, and reduce halo artefacts; but
more generally they should be closer to the colours resulting from
combinations of coloured filters or backlit transparencies.

### Sample images

#### Source images:

[[Linear-Light-Orig-Cityscape.png]] [[Linear-Light-Orig-Trumpeter.png]]

#### Non-linear compositing results

This is what MyPaint currently does.
Trumpeter image composited at 50% src-over the cityscape image.

[[Linear-Light-Output-Nonlin-Comp.png]]

#### Linear compositing results

Results of an old test branch with linear compositing,
uses the same source images and exactly the same compositing parameters

The layers are stored and composited in "linear light", i.e. with
numerical red, green and blue values proportional to absolute brigtness
values, then converted to a nonlinear display space for the sake of
display hardware that's either a CRT or an emulation of one (and also
the human eye!)

[[Linear-Light-Output-Lin-Comp.png]]

#### The effect on scaling

This image shows effect linear light has when zooming lineart. At the
top is the original size, at the bottom the zoomed-out image, before and
after implementing linear light. (View at full size for best
comparision).

[[Linear-Light-Scaling.png]]

You can also watch the [linear\_light\_scaling.ogv](http://maxy.log2.ch/misc/linear_light_scaling.ogv) screencast to see the difference.

### Consequences

Brush designers may need to update particularly low-alpha brushsets
(i.e. particularly soft or loose-edged brushes) because this change
affects the way alpha-blended stuff is laid down on the canvas.

Old files will not look the same as they did in linear-light versions
unless we have a backwards-compatibility mode.

### Status

Before the push to 1.2, a linear light branch was crated for testing[1](https://gitorious.org/~achadwick/mypaint/achadwick-mypaint/commits/linear-light-everywhere), but work was abandoned to concentrate on necessary UI changes.

Future work should be coordinated via these issues:

* https://github.com/mypaint/mypaint/issues/4
* https://github.com/mypaint/mypaint/issues/6
* https://github.com/mypaint/mypaint/issues/265

The transition from nonlinear to linear is not managed properly yet;
we'll need some agreement on the CREATE list and a note in the
OpenRaster draft spec regarding how we encode legacy and new-style
files, and what the default should be.

## See also

- <https://en.wikipedia.org/wiki/Digital_compositing>
- <http://www.artbeats.com/assets/written_tutorials/pdfs/linear_light.pdf> (sample images are a hat-tip to this tutorial's explanation!)
- <http://www.blender.org/development/release-logs/blender-256-beta/color-management/>
- <http://i.imgur.com/R601GRQ.png>

