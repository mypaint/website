The Lines and Curves tool is a geometrical tool to draw straight lines or smooth curves. The stroke shape can be modified directly after it is drawn to edit the curve. There are different ways to choose the Lines and Curves tool:
* Click on the Lines and Curves icon in the Toolbar
* Select _Edit → Lines and Curves_ from the top menu
* Select _Edit → Current Tool → Lines and Curves_ from the top menu
* or press the shortcut key `K`

![Lines and Curves](https://cloud.githubusercontent.com/assets/6949092/21074739/b64b7798-bf00-11e6-84dc-94bd6621b7a7.PNG)

### Drawing a line
Press down your left mouse button or graphics pen at the starting position of the stroke. Move your mouse or pen to the end position of your line and release the button (or lift your pen) to finish the stroke.
* Hold down `Ctrl` to snap the line angles

![Line + with Ctrl](https://cloud.githubusercontent.com/assets/6949092/21074817/9a026e6e-bf02-11e6-8c67-6c76e812ff82.gif)

### Turning a line into a curve
Pressing the left mouse or pen with `Shift` will modify the **last drawn** line. If there is no line one the canvas you will draw a new straight line. Changing the tool will deactivate the last drawn line. So be sure to finish your curve before you draw the next line or change the tool. You can move your cursor while manipulating the curve to make fine adjustments. You do not need to click and drag on the line, it will automatically bend towards your position.

* Hold` Shift` and click the first time to curve the line towards your cursor position.
* If you edit the curve a second time your cursor position is important. You will add a second bend to the curve at the starting point or ending point. It depends which one is closer to your cursor. The other point will inherit the curvature of your first modification.
* More edits: You will always manipulate the bend of the point you are closest to.

![Manipulating a curve](https://cloud.githubusercontent.com/assets/6949092/21075178/e364f870-bf0b-11e6-9fd6-1164666fe54c.gif)

### Further reading
The curves represent [[Bézier Curves|https://en.wikipedia.org/wiki/B%C3%A9zier_curve]], even though MyPaint does not display the handles. With the first manipulation the line is turned into a [[quadratic Bézier curve|http://blogs.sitepointstatic.com/examples/tech/svg-curves/quadratic-curve.html]]. With more manipulations it turns into a [[cubic Bézier curve|http://blogs.sitepointstatic.com/examples/tech/canvas-curves/bezier-curve.html]].
