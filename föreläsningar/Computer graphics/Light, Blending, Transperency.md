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
	- as when you look into the sun it blinds you, making other surfaces glow/becom blurry
- makes a suface able to almost glow when reflecting light (since its over 100%)
	- if a mirror reflects the sun, you should use HDR to make the reflection show the correct light, blinding.
### Global illumination 
- pbr is local illumination
- lightning beyond local calculations
	- example: light bounces from one surface to another and so on. This makes it so that each surface gets multiple light rays from different objects as it bounces with different values, light has no end position as in pbr and hdr.
	- local lightning just calculates the light of an object while global llumination also reflects the light to impact the surroundings
		- local lightning
			- takes the light value
		- global illumination
			- takes the light value and sends it back out with a different value depending on the objects material and reflection value 
- very expensive

- global light influence

### baked lightning
- if the light is static
	- Calculate the lightning
	- save it as a lightmap
	- apply the lightmap on the teture 
	- when rendering, apple the real time lighting on top of the lightmap
		- is in a room with a torch, the surroundings is a lightmap while the character/moving objects are real time rendered

### aplha blending
- the value of a pixel determines the opacity
	- used to make intricate designs or semi transparent glowing orbs
		- as you can "cut out" a form on a texture map (like leaves) and make everything else exept the form fully transparent

### Blending modes
- 2 common modes
	- normal/over
	- additive
- ### rendering order
	- alpha blending is usually order dependent
	- game ingines renders transparent objects after opaque objects and sorted back-to-front
