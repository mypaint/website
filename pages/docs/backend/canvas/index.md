+++
title = "Canvas"
summary = "How MyPaint renders the canvas"
mypaintver = "v3.0.0"
+++

# Surface Format and Rendering
![Tiled surface](Development-Documentation-Tiled-surface.png)
![Tiled surface incremental](Development-Documentation-Tiled-surface-incremental.png)
 -- incremental screen updates during a stroke

MyPaint stores its pixel data inside tiles of a fixed size. The *TiledSurface* class allocates memory just for the tiles that you paint on. When the screen is updated, the tiles are composited into a temporary rectangular pixbuf, which is then passed to [Cairo](http://www.cairographics.org/) for rotated and zoomed rendering.

During painting, all tiles touched by the stroke are composited completely, but the update region is clipped to the bounding box of the new dabs.

# Pixel Format
MyPaint's internal pixel storage uses tiled surfaces where each tile is a square pixel array of side N (currently 64), organized top-to-bottom and left-to-right. These memory areas are also the data segment of a NumPy array of dimensions (N, N, 4), and the data type uint16. Pixels are stored as RGBA data using an unusual but speedy "15+1"-bit floating point value where 0x8000 (1\<\<15) represents 1.0 and 0x0000 represents 0.0. Pixel R, G, and B values are stored multiplied by the pixel's alpha component and are currently nonlinear with an assumed sRGB gamma curve.

- [Pixel Format blog entry](http://mypaint.intilinux.com/?p=19)

New code should use the inline functions defined in `fix15.hpp` for clarity.

In some (but not all) rendering contexts we ignore the backdrop's alpha for speed, and assume that it's always 1.0. Historically, MyPaint has always rendered layers over a solid background, but as of the current development master, this is changing.
