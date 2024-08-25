+++
title = "HCY Wheel and Gamut Mask Editor"
+++

### HCY Wheel Colour Selector

* Open with _Menu → Colour → **HCY Wheel**_.
* The **HCY Wheel** is also listed in the colour dropdown menu on the toolbar.

[[v1.2-HCY-Wheel.png]]

The HCY Wheel colour selector looks like a disc of colour next to a bar that controls brightness. It can be docked into a sidebar or floated free. The disc's centre holds the least saturated form of all the hues around the edge of the disc. Click or drag on the disc to set a hue and saturation, and on the bar to pick a brightness.

The wheel uses an HCY (Hue, Chroma, Luma) colour model where each point on the disc for a given L has something fairly close to the same brightness as perceived by the human eye, if your monitor is calibrated and colour corrected in a standard way. This makes it a good system for choosing limited-palette colour schemes using a technique called Gamut Mapping, or Gamut Masking.

### Gamut Masks

* [YouTube video demonstrating Gamut Masking](https://www.youtube.com/watch?v=qfE4E5goEIc), by James Gurney

Gamut masks are like a piece of tracing paper with cut-out holes, placed over the colour wheel to limit the range of colours you can select. This allows you to plan your colour schemes in advance, which is useful for colour scripting or to create specific moods. The theory is that the corners of each mask shape represent a subjective primary colour, and that each shape contains all the colours which can be mixed using those corner primaries. Subjective secondary colours lie at the midpoints of the shape edges, and the centre of the shape is the subjective neutral tone for the shape.

### Gamut Mask Editor

* Click on the wrench icon shown above to open the mask editor dialog.

[[v1.2-Gamut-Mask-Editor.png]]

You can edit the gamut mask here, or turn it off or on.

Click to add shapes if the wheel is blank. Shapes can be dragged around and their outlines can be adjusted by adding or moving the control points. Make a shape too small to be useful to remove it: dragging a shape to the edge of the disc is a quick way of doing this. You can delete shapes by dragging them inside other shapes too. The entire mask can be rotated by turning the edge of the disc to generate new and unexpected colour schemes.

The New button lets you choose one of several templates as a starting point:

[[v1.2-Gamut-Mask-Templates.png]]

Gamut masks can be saved to GIMP-format palette files, and loaded from them. The gamut mask is not currently saved inside an OpenRaster working file, but I'd like to add the ability to do that in a future version.
