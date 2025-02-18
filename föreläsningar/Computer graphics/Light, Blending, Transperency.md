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

### PBR mode.
(physically-based rendering)
- Texture based maps specify how light is affecting the material, one property per map	
- four maps are common, but more can be used
#### Unity PBR shader
- diffuse-term is based on Burley (2012)
- Speular-term is based on Walter, Marschner and Torrance (2007)

- Albedo
	- base color of the material when fully lit
- Roughness/smoothness
	- grayscaleimage that affects how light is refleced when ih hits the surface
		- black = light scatters in all directions
		- white= light bounces straight
- Metallic
	- is the material metal or not?
	- is often set to either 0 or 1
		- is either metallic or not
- Height/Displacement
	- used for Parallax mapping
	- creates a sense of peth(fake sense)
		- requires low computational power
	- Gray(0.5f) means "ground level"
- Ambient Occlusion
	- how much does the material self-shadow
- Emission
	- is the material visible even if no light hits it
	- often has an own light source
- secondary maps
	- second albedo/normal map
	- applied on top of an eisting map to get more details
	- is often repeated multiple times

### HDR
higher dynamic range
- can be higher than 100%
- can bleed over other surfaces
	- as when you look into the sun it blinds you, making other surface