+++
title = "Tool Options Panel"
+++

The tool option panel shows different options depending on the active tool. There are some tools without options. Other tools have very similar options.

## Painting Tools - Tool Options Panels
![Freehand Tool Options](https://cloud.githubusercontent.com/assets/6949092/21095114/548baef0-c05a-11e6-9549-e0713a5d91b8.PNG)![Lines and Curves Tool Options](https://cloud.githubusercontent.com/assets/6949092/21095119/5970259a-c05a-11e6-8279-0a6f37e31270.png)![Connected Lines Tool Options](https://cloud.githubusercontent.com/assets/6949092/21095122/5c4bf4d8-c05a-11e6-914d-8297f734573a.png)![Circle and Ellipses Tool Optios](https://cloud.githubusercontent.com/assets/6949092/21095133/670dc00e-c05a-11e6-917a-fb4b720850ad.png)

* Tools: [[Freehand|v1.2-Freehand-Tool]], [[Lines and Curves|v1.2-Lines-and-Curves]], [[Connected Lines|v1.2-Connected-Lines]], [[Ellipses and Circles|v1.2-Ellipses-and-Circles]]
* All controls in this Option panel are connected to the Brush Editor window. They are shortcuts to quickly tweak brush settings.
* Brush settings:
  * **Size** - Changes the base value of the Radius brush setting
  * **Opaque** - Changes the base value of the Opacity brush setting
  * **Sharp** - Changes the base value of the Hardness brush setting
  * **Gain** - Change the base value of the Pressure Gain brush setting
  * **Smooth** - Changes the base value of the Slow Position Tracking brush setting. Freehand only.

* The Pressure variation graph simulates pen pressure input for geometrical shapes. The actual pressure value is also influenced by the Gain setting. The saved brush settings define how this pressure input affects appearance. There are four points on the graph. 
  * X axis: left - beginning, right - end of stroke
  * Y axis: top - high pressure, bottom - low pressure

* **Reset** button - Loads the saved values of the brush

### Inking Tool Options Panel
![Ink Tool Options](https://cloud.githubusercontent.com/assets/6949092/21095123/6045663c-c05a-11e6-9f88-87af749b37e6.png)

The [[Inking Tool|v1.2-Inking-Tool]] allows you to edit a stroke after it has been drawn. It helps you to use brush setting inputs, that are not supported by your hardware (e.g. pressure with a mouse). The Tool Options Panels offers sliders to change the input values for selected nodes. And buttons to manage all nodes on the stroke.

* **Press** - Change the recorded pen pressure for the selected node.
* **X-Tilt** - Change the recorded pen tilt in the X direction.
* **Y-Tilt** - Change the recorded pen tilt in the Y direction.
* **Time** - Change the time it took to draw from the previous node to the selected node. This basically changes the recorded speed.
* **Delete Point** - deletes selected node.
* **Simplify Points** - analyses the path and deletes nodes that are not necessary to maintain the shape.
* **Cull Points** - deletes each other point, bringing the node count down to a half.

### Flood Fill Tool Options Panel
![Flood Fill Tool Options](https://cloud.githubusercontent.com/assets/6949092/21095135/696b22a6-c05a-11e6-94ec-d8d602ab7700.png)  

Use the Tool Option Panel to adjust the behavior of the [[Flood Fill Tool|v1.2 Flood Fill Tool]].
* **Tolerance** - A high tolerance will also fill similar colours or transparencies.
* **Source: Sample merged**
  * Disabled: Only the current layer is sampled to find the area to fill
  * Enabled: The layers are temporarily merged to find the area to fill
* **Target: New Layer (once)** - The filled area will be added as a new layer.
* **Reset** button - Resets to default settings.

### Frame Tool Options Panel
![Frame Tool Options](https://cloud.githubusercontent.com/assets/6949092/21118843/0a550794-c0c0-11e6-9f4a-6a37b2b96db6.png)

The [[Frame Tool|v1.2 Frame Tool]] allows you to set borders on the ipnfsinite canvas. You can set up, customize and modify the frame in the Tool Options Panel:
* Numeric Size button - The size in pixels is displayed here. Click this button to open a popup window where you can enter precise values for the frame size and dpi.
* Colour: Click on the button to open a popup where you can change the colour of the masked area.
* Enabled checkbox - Show or hide the frame. All frame setting will be stored even when the frame is hidden.
* Set Frame to Layer button - Fit the frame around all content of the active layer.
* Set Frame to document button - Fit the frame around the whole content on all layers.
* Trim Layer to Frame - This will delete content from a layer that is masked by the layer box

### Symmetry Tool Options Panel
![Symmetry Tool Options](https://cloud.githubusercontent.com/assets/6949092/21095145/7163d75a-c05a-11e6-80fe-0c471a39100f.PNG)

The [[Symmetry Tool|v1.2 symmetry Tool]] mirrors the brush strokes on an axis. The Tool Option Panel helps you to set up symmetry:
* Alpha - Makes the symmetry line more transparent or more opaque.
* Position button - Shows the numeric value. Can be clicked to change it.
* Enabled checkbox - Shows or hides the symmetry axis.
