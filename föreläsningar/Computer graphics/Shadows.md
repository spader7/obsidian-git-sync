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
- fragments far away are drawn first. and the closer ones are drawn ontop
- issue: sorting objects is not always well defined
- solution: dividing concave meshes into multiple parts that can be sent to the render pipeline separately
### Depth buffer
- we introduce new render target called "depth buffer"
	- when rendered, z.coordinate (in view space) is stored in the depth buffer
	- when rendering, check depth buffer if new fragment is infront or behind. 
		- if behind, dont render invisible parts
- Better at handling concave objects
- can be combined with z-culling to optimize
- bad at handling transparency
- requires more memory access
- Issue: z-fighting
	- when 2 objects are too close, it becomes an issue of which object to render
	- solution:
		- move triangles slightky apart
		- chage camera near/far settings
		- increase z-bias
		- turn off z-write for objects known to be behind everything else
### shadows vs shading
- shading: the intensityof thelight hitting each side of an object