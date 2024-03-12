+++
title = "Merging and Normalizing Layers"
+++

MyPaint allows you to merge two or more existing layers in your work together, compacting them to save on disk space and computational overhead. There are a number of commands available from the Layers menu which perform layer merges or similar operations.

* [Merge Layer Down](#merge-layer-down)
* [Merge Visible Layers](#merge-visible-layers)
* [New Layer from Visible](#new-layer-from-visible)
* [Convert to Normal Painting Layer](#convert-to-normal-painting-layer)

:warning: At the time of writing this documentation for v1.2.x, all these operations perform a backdrop subtraction operation as a final stage. [Backdrop subtraction](#backdrop-subtraction) is a unique feature of MyPaint which allows merge and normalize operations to be very accurately previewed before you perform them, but it can be somewhat surprising. More below.

## Merge and Normalize operations

#### Common characteristics

* These operations always result in an ordinary painting layer with a layer mode of _Normal_, at 100% opacity.
* Layer names are preserved, comma-separated, if they are informative. "Informative" means any name which isn't just the default name for its layer's type, followed by a number.
* The strokemaps are preserved if the layers being merged or normalized are painting layers.

#### Merge Layer Down

This operation merges the current layer and the one beneath it into a single layer.
The merge-down command is not always available.

* Merge Down can't merge the current layer with a layer outside its own group.
* Merge Down can't be used on the bottom layer of a stack.
* You can't Merge Down some combinations of layer modes.
For example, you can't merge down onto certain kinds of masking layer.

When the Merge Down command is unavailable,
its button and menu item is greyed out.

You _can_ Merge Down with groups.
If either layer is a group, it gets [normalized](#convert-to-normal-painting-layer) first.

#### Merge Visible Layers

All of the layers marked as visible in the Layers dock-panel will be deleted, and replaced with the result of merging them - minus the backdrop to the merge, of course. For this kind of merge, the only backdrop element which can matter is the background paper texture. Turn the background off if you want to avoid it getting incorporated into the merge result.

#### New Layer from Visible

This works just like Merge Visible Layers, but the originals are not deleted. Since the results of the merge are shown on top of the inputs to the merge, this command won't follow the otherwise quite strict WYSIWYG pattern of the other merges and the normalize operation where the results have transparency - which they quite often do after background subtraction.

#### Convert to Normal Painting Layer

This applies the normalize operation to the current layer, replacing it with an identical-looking ordinary painting layer at 100% opacity and with a mode of _Normal_.

:ghost: Using this command on a layer can make it take on a ghost image of its backdrop, just like the layer merge commands. The ghost image comes about due to MyPaint's background subtraction step. You can make the effect more predicable by making the layers below the layer to be normalized invisible and turning off _Show Background_.

## Backdrop Subtraction

When merging or normalizing layers, MyPaint always renders the layers it needs with the backdrop incorporated into the merged layer, and then subtracts the backdrop from the merged layer. Formally speaking, the "backdrop" is the cumulative result of compositing all of the layers underneath the layers you are merging or normalizing. The layers which contribute to the backdrop of a merge or normalize operation can be limited by grouping the layers to be merged, unless the layer group has its mode set to _Pass-through_.

The background paper texture will often form part of the backdrop, unless _Show Background_ is turned off, or your layers are grouped in a normal fashion.

:gift: This allows merge and normalize operations to be very accurately previewed on screen before you perform them (even layers with effects like Plus), at the cost of some extra thought

