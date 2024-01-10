# Info
- This is a list of untested keywords that I found through digging around. It is best to ignore these but if you want to try them out, have at it.
- I will be listing these keywords under the shader I believe it will work for.
- The shader names I will use are the ones listed in Unity that get put on geo, not the shader names from Chroma as I suspect the one listed by Unity is the important one.

### Stuff to keep in mind
- I know nothing about materials, shaders, and shader keywords.
- I know VERY little about Unity.
- I got these keywords from like 100 different sources from within the game so I don't know how many of these are valid keywords. (I probably have missed some or added some that are not even a thing)
- I have not tested every keyword listed here.

### Shader List
Here is a list of what shader each Chroma shader uses:
- Standard = SimpleLit
- OpaqueLight = OpaqueNeonLight
- TransparentLight = TransparentNeonLight
- BaseWater = WaterLit
- BillieWater = WaterLit
- BTSPillar = SimpleLit
- InterscopeConcrete = SimpleLit
- InterscopeCar = SimpleLit
- WaterfallMirror = Mirror

# Keywords List
- [SimpleLit](README.md#SimpleLit)
- [OpaqueNeonLight](README.md#OpaqueNeonLight)
- [TransparentNeonLight](README.md#TransparentNeonLight)
- [WaterLit](README.md#WaterLit)
- [Mirror](README.md#Mirror)


## SimpleLit
- "ENABLE_METAL_SMOOTHNESS_TEX"
- "SPECULAR_ANTIFLICKER"
- "PRECISE_NORMAL"
- "DISPLACEMENT_SPATIAL"
- "SPECTROGRAM"
- "EMISSION_TWICE"
- "INVERT_PULSE"
- "PULSE_MULTIPLY_TEXTURE"
- "EMISSION_MASK"
- "DECAL_TEXTURE"
- "DIFFUSE"
- "LIGHT_FALLOFF"
- "INVERT_DIFFUSE_NORMAL"
- "BOTH_SIDES_DIFFUSE"
- "PRIVATE_POINT_LIGHT"
- "INSTANCED_PRIVATE_POINT_LIGHT"
- "DIFFUSE_TEXTURE"
- "SPECULAR"
- "LIGHTMAP"
- "NORMAL_MAP"
- "USE_SPHERICAL_NORMAL_OFFSET"
- "REFLECTION_TEXTURE"
- "REFLECTION_PROBE"
- "REFLECTION_PROBE_BOX_PROJECTION"
- "ENABLE_RIM_DIM"
- "GROUND_FADE"
- "DIRT"
- "DIRT_DETAIL"
- "ROTATE_UV"
- "UV_COLOR_SEGMENTS"
- "HIGHLIGHT_SELECTION"
- "FOG"
- "HEIGHT_FOG"
- "HEIGHT_FOG_DEPTH_SOFTEN"
- "DISTANCE_DARKENING"
- "ENABLE_HOLOGRAM"
- "ENABLE_DISSOLVE"
- "CUTOUT"
- "NOISE_DITHERING"
- "LINEAR_TO_GAMMA"
- "SONG_TIME"
- "MESH_PACKING"
- "DISSOLVE_DISPLACEMENT"
- "ENABLE_HEIGHT_FOG"
- "ENABLE_HEIGHT_FOG_SOFTEN"
- "ENABLE_RIM_DIM"
- "ENABLE_GROUND_FADE"
- "ENABLE_DIRT"
- "ENABLE_DIRT_DETAIL"
- "ENABLE_FOG"
- "ENABLE_DISTANCE_DARKENING"

## OpaqueNeonLight
- "ENABLE_HEIGHT_FOG"

## TransparentNeonLight
- "ENABLE_HEIGHT_FOG"
- "ENABLE_WORLD_NOISE"
- "ENABLE_WORLD_SPACE_FADE"
- "SPECULAR"
- "NORMAL_MAP"
- "REFLECTION_PROBE"
- "ENABLE_RIM_DIM"
- "INVERT_RIM_DIM"

## WaterLit
- "ENABLE_METAL_SMOOTHNESS_TEX"
- "SPECULAR_ANTIFLICKER"
- "Z_FADE"
- "Y_FADE"
- "EMISSION_TWICE"
- "INVERT_PULSE"
- "PULSE_MULTIPLY_TEXTURE"
- "EMISSION_MASK"
- "RIMLIGHT_LERP"
- "RIMLIGHT_ADDITIVE"
- "DIFFUSE"
- "LIGHT_FALLOFF"
- "INVERT_DIFFUSE_NORMAL"
- "BOTH_SIDES_DIFFUSE"
- "PRIVATE_POINT_LIGHT"
- "DIFFUSE_TEXTURE"
- "SPECULAR"
- "LIGHTMAP"
- "NORMAL_MAP"
- "DETAIL_NORMAL_MAP"
- "USE_SPHERICAL_NORMAL_OFFSET"
- "REFLECTION_TEXTURE"
- "REFLECTION_PROBE"
- "REFLECTION_PROBE_BOX_PROJECTION"
- "REFLECTION_PROBE_BOX_PROJECTION_OFFSET"
- "ENABLE_RIM_DIM"
- "INVERT_RIM_DIM"
- "GROUND_FADE"
- "DIRT"
- "DIRT_DETAIL"
- "ROTATE_UV"
- "ENABLE_FOG"
- "ENABLE_HEIGHT_FOG"
- "NOISE_DITHERING"
- "LINEAR_TO_GAMMA"

## Mirror
- "DETAIL_NORMAL_MAP"
- "LIGHTMAP"
- "DIFFUSE"
- "SPECULAR"
- "ENABLE_DIRT"
