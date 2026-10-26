Q: Why does Builds go up by one per second and not by two? What error would you see in the console if the widget left the screen and timer.cancel() was missing from dispose?
A: Builds goes up by one per second because setState() runs once per timer tick, triggering a single rebuild. If timer.cancel() is missing, the timer keeps running in the background and tries to call setState() on a disposed element, causing a console error and a memory leak.

Q: Which one is "cheap and thrown away" versus which one keeps the State?
A: The Widget is cheap and completely thrown away and recreated on every rebuild. The Element stays alive in the background tree across rebuilds and maintains the link to the State.

Q: Why does Flutter prefer composition over inheritance for building custom components like Tile?
A: Composition lets us combine smaller built-in widgets together instead of creating complex subclasses. It keeps our code much more flexible and avoids rigid inheritance hierarchies.

Q: Without keys, why did the number stay at the left even though the label moved? Use the words widget, Element and State in your answer.
A: Without keys, Flutter matches widgets by their position in the tree. The Element and its associated State stayed anchored at index position 0, while only the new Widget label was rendered into that position. With ValueKeys, the Element tracks the key instead of the position, so the State moves together with the widget.

Q: In a Column, which axis is the main axis? Why does crossAxisAlignment: CrossAxisAlignment.center in a Column move the children left or right and not up or down?
A: In a Column, the main axis is vertical. The cross axis is horizontal, which is why crossAxisAlignment controls horizontal alignment, moving the children left or right instead of up or down.

Q: Why does wrapping a Text in Expanded make it wrap its words? Use the idea "constraints go down, sizes go up" from slide 13.
A: Constraints go down, sizes go up. A Row gives its children unconstrained horizontal space by default, causing overflow. Wrapping in Expanded forces a tight upper width constraint down onto the Text, forcing it to break and wrap its words inside that bounded width.

Q: What would change on the screen if you swapped Expanded and Flexible between the two buttons? Which one is "Flexible with fit: tight"?
A: If swapped, the button with Flexible would shrink to its text width while the one with Expanded would stretch fully. Expanded is "Flexible with fit: tight".

Q: Why does Container require color to be placed inside BoxDecoration when a decoration is specified?
A: Because the BoxDecoration handles painting properties (background, border, gradient, shadow). Flutter separates layout/sizing from painting to optimize rendering efficiency.