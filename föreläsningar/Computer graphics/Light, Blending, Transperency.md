[[Rasterization]]
- Virtual light source: point in space
- Differs in light "spread"


### Flat shading
	- calculate where the light comes from
### Phon shading model
	- Ambient: color of the surroundings
	- Diffuse: color of the material
	- Specular: color of th light
### Diffuse shading
- calculate the light shading deoending on the angle
```c#
diffuse = cos(0) // where 0 is the angle
diffuse = max(0, cos(0)) //max returns the max of 2 values
î= i(vector)/||i||(length)
cos(0) = î * ^n //i and n are 2 vectors
```
diffues = max(0,î*^n)
specular = max(0,^r*ê)p(p in square)