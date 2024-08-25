+++
title = "Layers Panel"
+++

The Layers dockpanel is used for organizing files into layers and groups of layers.
It can be opened from the main application menu (_Window → Layers Panel_),
or by clicking its icon on the toolbar.

[[v1.2-Layers-Panel-toolbar-icon.png]]

### Layers panel layout

The panel's UI is fairly complex.

[[v1.2-Layers-Panel.png]]

From top to bottom, it contains:

* The _mode menu_, for selecting [[how the layer combines with its underlying layers|v1.2 Layer Modes]].
* The _opacity slider_, which controls how much of the layer's content combines with its underlying layers.
* The _layers tree_, sometimes called the _layer stack_.
  * The icon on the left represents the type of the layer.
    * Folder icons represent groups.
    * Normal painting layers don't get any special icon.
    * Special kinds of layer get different icons.
  * Grid lines and spinner triangles help you organize the tree structure.
  * Layers can be dragged and dropped within the tree.
  * Layer groups are treated much like layers. Their name is shown in italics.
  * The _eye icon_ ![open eye](https://cdn.rawgit.com/mypaint/mypaint/dc5b32376520a6b2dc5b55516dd202ecc5c709c8/desktop/icons/hicolor/scalable/actions/mypaint-object-visible-symbolic.svg) controls whether the layer is visible.
  * The _lock icon_ ![open padlock](https://cdn.rawgit.com/mypaint/mypaint/dc5b32376520a6b2dc5b55516dd202ecc5c709c8/desktop/icons/hicolor/scalable/actions/mypaint-object-unlocked-symbolic.svg) controls whether the layer is locked for edits.
* Actions which affect the currently highlighted layer. From left to right:
  * _Add Layer_: add a new layer above the current one.
  * _Remove Layer_: remove the current layer.
  * _Move Layer Up_, and **Move Layer Down**: these move the layer around in the tree.
  * _Duplicate Layer_: this makes an exact copy of the current layer (or group) at its current location.
  * _Merge Layer Down_: merge the layer into the one below it, if that's possible. :ghost: [[Be careful, this can change the two layers' appearance unexpectedly!|v1.2 Layer Merging and Normalization]]
* The _Show Background_ toggle turns MyPaint's special background layer on or off. The button next to it allows a different background image to be chosen.

### The background layer

This is a special hidden layer which can be thought of as an infinite piece of drawing paper.
Images do not have to contain a visible background layer.
The background layer can be turned off, in which case it is replaced with checker-board pattern.
When the background layer is turned off, some actions in MyPaint have different outcomes:

* When saving or exporting to a PNG image, the background layer is not included.
* When merging layers, the effect is “more correct”, and not as prone to ghosting. See [[v1.2 Layer Merging and Normalization]] for details.



