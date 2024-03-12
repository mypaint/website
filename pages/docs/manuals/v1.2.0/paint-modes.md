+++
title = "Paint Modes"
+++

_Paint modes_, also known as _brush blend modes_, change the way that the brush applies paint. They affect every kind of drawing and painting tool where you use the brush to apply paint. MyPaint's paint modes track the current brush, so if you choose an eraser preset from a brush group panel, you will see the Eraser symbol on the toolbar light up.

**TODO:** this page needs illustrated examples like [[v1.2 Layer Modes]]

### Normal
![Normal example, orange swirl with transparency visible](https://cloud.githubusercontent.com/assets/6949092/20886708/9f42e26e-baf7-11e6-97c3-8ad659813a6e.png)
* Menu: _Brush → Paint Mode → Paint Mode: Normal_
* Key: `N`
* Toolbar: no button.

This is normal overpainting, identical to the Normal layer mode. To get back to Normal paint mode, press "N" or disengage the current paint mode using the toolbar. It's identical to the [[“Normal” layer mode|v1.2 Layer Modes#normal]].

### Eraser
![Eraser: Normal image erased with varying transparency](https://cloud.githubusercontent.com/assets/6949092/20886709/9f4347e0-baf7-11e6-9a7a-ee02908189df.png)

* Menu: _Brush → Paint Mode → Paint Mode: Eraser_
* Key: `E`
* Toolbar: Eraser icon in the [[Core Tools|v1.2 Main Toolbar#core-tools]] section.

This changes the current brush to act as an eraser.

### Lock Alpha
![Lock: Normal image painted with darker cyan](https://cloud.githubusercontent.com/assets/6949092/20886707/9f3fc3e0-baf7-11e6-893e-d0b501090e6d.png)

* Menu: _Brush → Paint Mode → Paint Mode: Lock Alpha_
* Key: `Shift+L`
* Toolbar: Padlock icon in the [[Blend Modes|v1.2 Main Toolbar#blend-modes]] section.

Applying the brush doesn't change the transparency of the pixels you paint over in the current layer. It's identical to the [[“Source Atop” layer mode|v1.2 Layer Modes#source-atop]].
Use this for further highlighting or shading objects that are painted on their own layer.
It's analogous to painting on layer groups which contain a mask, but a lot less fiddly.

### Colourize
![Colourize: Dark cyan is changed to the same brightness as the orange](https://cloud.githubusercontent.com/assets/6949092/20886710/9f4bf0f2-baf7-11e6-8303-6abc9dab064c.png)
* _Brush → Paint Mode → Paint Mode: Colourize_
* `Shift+K`
* Toolbar: Rainbow icon in the [[Blend Modes|v1.2 Main Toolbar#blend-modes]] section.

Painting applies the hue (kind of colour) and saturation (degree of colour) of your brush to whatever you paint on. The value (brightness or darkness) of what you paint on isn't affected. It's identical to the [[“Colour” layer mode|v1.2 Layer Modes#color]].
Use this for adjusting colours, or assigning colour to something you've painted in greyscale.

Like Lock Alpha, Colourize mode also doesn't change the transparency of what you paint on.
