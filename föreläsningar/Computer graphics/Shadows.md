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
- shading: the intensity of the light hitting each side of an object
- shadows: the way other objects obstruct the light source
	- caster: the object obstructing the light
	- reciever: the object that the shadow falls on
- issue: hot to determine if an object is in shadow whe we are sending one object at a time to the gpu
- solution shadow map
### shadow maps
- virtual camera drawn from the perspective of each light
- depth buffer of that camera stored in a new render texture
- Different light generates different shadow maps
	- spotlight
	- directional light
		- orthographic perspective camera
			- follows the main camera
	- point light
		- generate a cube of shadow maps (6 cameras)
- shadow map issues:
- shadow acne/ self shadowing
	- when the light angle is close to the same angle as a surface