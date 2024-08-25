+++
title = "Layer Modes"
+++

## Supported Layer Modes

MyPaint supports the
[layer blending modes](https://wiki.freedesktop.org/www/Specifications/OpenRaster/Draft/LayersStack/)
documented in the OpenRaster specification, version 0.0.5.
These are useful combinations of the layer blending and compositing modes defined
in the [W3C Compositing and Blending Level 1 Editor’s Draft](http://dev.w3.org/fxtf/compositing-1/)
as of 2015-10-28.

A layer can be assigned one of these modes using the [[Layers Panel | v1.2 Layers Panel]].
The blending mode of a layer determines how its pixels combine with the pixels of its backdrop.

### Comparison Chart

| Purpose | . | .. | ... | .... |
|---------|---|----|-----|------|
| Stacking layers simply. | [![Normal][normal]](#normal)
| Darkening or shading. | [![Multiply][multiply]](#multiply) | [![Darken][darken]](#darken) | [![Burn][burn]](#burn)
| Lightening or highlighting. | [![Screen][screen]](#screen) | [![Lighten][lighten]](#lighten) | [![Dodge][dodge]](#dodge) | [![Plus][plus]](#plus)
| Combining bright and dark parts of both layers. | [![Overlay][overlay]](#overlay) | [![Hard Light][hard-light]](#hard-light) | [![Soft Light][soft-light]](#soft-light)
| Inverting the top image. | [![Difference][difference]](#difference) | [![Exclusion][exclusion]](#exclusion)
| Changing hue, saturation, or brightness. | [![Hue][hue]](#hue) | [![Saturation][saturation]](#saturation) | [![Color][color]](#color) | [![Luminosity][luminosity]](#luminosity)
| Masking areas. | [![Destination In][destination-in]](#destination-in) | [![Destination Out][destination-out]](#destination-out) | [![Source Atop][source-atop]](#source-atop) | [![Destination Atop][destination-atop]](#destination-atop)

### Basic Modes

The basic [blend modes][wikipedia-blend-modes] combine the RGB pixels of the top layer with its backdrop to create some effect, then composite the result of the blending step over the backdrop using standard [alpha compositing][wikipedia-alpha-compositing].

#### Normal

![Preview of “Normal” mode][normal]

The “Normal” mode is the default.
It combines the top layer with the one below it,
without first changing any of the colors in the top layer,
and using standard alpha compositing.

“Normal” mode can be applied to layer groups.
It causes the group’s content to be calculated in isolation
before the result is then composited onto the group’s backdrop.

#### Pass-through

(No preview)

“Pass-through” mode can only be applied to layer groups.
Assigning pass-through mode to a group
makes each layer within the group affect the _group’s_ background.

#### Multiply

![Example of “Multiply”][multiply]

“Multiply” mode is similar to
loading two slides into a projector,
then projecting the combined result.

#### Screen

![Example of “Screen”][screen]

“Screen” mode is like
shining two separate slide projectors onto a screen simultaneously.
This is the inverse of [Multiply](#multiply).

#### Overlay

![Example of “Overlay”][overlay]

The backdrop is overlaid with the top layer, preserving the backdrop's highlights and shadows.
This mode is the inverse of [Hard Light](#hard-light).

#### Darken

![Example of “Darken”][darken]

The top layer is used where it is darker than the backdrop.

#### Lighten

![Example of “Lighten”][lighten]

The top layer is used where it is lighter than the backdrop.

#### Burn

![Example of “Burn”][burn]

“Burn” mode darkens the backdrop using the top layer.
The effect looks similar to
the photographic darkroom technique of the same name,
which is used for reducing over-bright highlights.

#### Dodge

![Example of “Dodge”][dodge]

“Dodge” mode brightens the backdrop using the top layer.
The effect is similar to
the photographic darkroom technique of the same name,
which is used for improving contrast in shadows.

#### Hard Light

![Example of “Hard Light”][hard-light]

“Hard Light” mode is similar to shining a harsh spotlight onto the backdrop.

#### Soft Light

![Example of “Soft Light”][soft-light]

“Soft Light” mode is somewhat like shining a diffuse spotlight onto the backdrop.

#### Difference

![Example of “Difference”][difference]

“Difference” mode subtracts the darker colour from the lighter of the two.

#### Exclusion

![Example of “Exclusion”][exclusion]

“Exclusion” mode is similar to [Difference](difference), but lower in contrast.

#### Plus

![Example of “Plus”][plus]

“Plus” mode adds together the layer and its backdrop.

### Color-and-Brightness Modes

These layer modes let you change the colour of the backdrop or its brightness.
They let you colourize a monochrome image,
desaturate it,
or tweak shadows and highlights.

These modes don’t operate on the usual red, green, and blue channels.
They operate on **hue**, **saturation**, and **luminosity** channels instead.
A pixel’s hue describes _what_ colour it is,
and its saturation measures _how strong_ that colour is.
Pixels also have luminosity, which is a measure of brightness.
This trio describes a pixel in enough detail to work on.
These modes blend new pixel trios from the top layer and its backdrop.

> :bulb: The luminosity measure these modes use is quite relevant to the human eye.
> It's the same kind of brightness a television uses.
> MyPaint's [[HCY wheel|v1.2 HCY Wheel and Gamut Mask Editor]] uses the same system.

The results of the colour blend then get composited over the backdrop in [the usual way][wikipedia-alpha-compositing].
This means you can use the layer’s opacity to adjust the amount of change you see.

#### Hue

![Example of “Hue”][hue]

“Hue” mode combines the hue of the top layer with the saturation and luminosity of the backdrop.

#### Saturation

![Example of “Saturation”][saturation]

“Saturation” mode combines the saturation of the top layer's colours with the hue and luminosity of the backdrop.

#### Color

![Example of “Color”][color]

“Color” mode combines the hue and saturation of the top layer with the luminosity of the backdrop.

#### Luminosity

![Example of “Luminosity”][luminosity]

“Luminosity” mode combines the luminosity of the top layer with the hue and saturation of the backdrop.

### Masking Modes

MyPaint v1.2.x has a primitive kind of layer mask.
These can be built using separate mask layers,
which are ordinary layers with a masking mode applied.

Masking modes implement a useful subset of the Porter-Duff compositing operators.

These primitive mask layers, and the layers they are applied to,
should typically be placed inside a layer group,
and these layer groups should use the default Normal mode.

#### Destination In

![Example of “Destination In”][destination-in]

“Destination In” uses the backdrop only where the top layer covers it.
Everything else is ignored.

#### Destination Out

![Example of “Destination Out”][destination-out]

“Destination Out” uses the backdrop only where the top layer *doesn't* cover it.
Everything else is ignored.

#### Source Atop

![Example of “Source Atop”][source-atop]

Parts of the top layer which overlap the backdrop replace the backdrop image.
The backdrop is used everywhere else,
and the combined effect takes on the bottom layer's shape.

#### Destination Atop

![Example of “Destination Atop”][destination-atop]

Parts of the bottom layer which *aren't* overlapped by the top layer are used verbatim.
The top layer is used everywhere else,
and the combined effect takes on the top layer's shape.


[normal]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Normal.png
[multiply]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Multiply.png
[screen]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Screen.png
[overlay]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Overlay.png
[darken]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Darken.png
[lighten]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Lighten.png
[dodge]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Dodge.png
[burn]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Burn.png
[hard-light]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Hard-Light.png
[soft-light]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Soft-Light.png
[difference]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Difference.png
[exclusion]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Exclusion.png
[hue]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Hue.png
[saturation]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Saturation.png
[color]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Color.png
[luminosity]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Luminosity.png
[plus]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Plus.png
[destination-in]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Destination-In.png
[destination-out]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Destination-Out.png
[source-atop]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Source-Atop.png
[destination-atop]: https://raw.githubusercontent.com/wiki/mypaint/mypaint/v1.2-Layer-Modes-Destination-Atop.png
[wikipedia-blend-modes]: https://en.wikipedia.org/wiki/Blend_modes
[wikipedia-alpha-compositing]: https://en.wikipedia.org/wiki/Alpha_compositing
