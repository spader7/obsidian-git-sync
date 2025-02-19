[[föreläsningar/Computer graphics/Rasterization|Rasterization]]

### Depth

### Render targets
- render pipeline processes primitives and outputs an image
	- this can be displayed directly or saved and be displayed later

### Rendering multiple objects
- you need to determine the order of rendering 
### Painter's Algorithm
- sort all objects based on distance from the camera before rendering
- render the primitived in  order of  "back to front"
- fragments far away are drawn first. and the closer ones are drawn 
- issue: sorting objects is not always well defined
- solution: dividing concave meshes into multiple parts that can be sent to the render pipeline separately