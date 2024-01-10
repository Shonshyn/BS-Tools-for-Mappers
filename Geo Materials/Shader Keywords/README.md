# Info
- Here is where I will list information regarding what I figure out about shader keywords as I mess around with them over time.
- I will list keywords found inside Chroma on this page. (For a larger, more-likely-to-not-work list, go [here](Unverified%20Keywords/README.md))
- The shader names I will use are the shader names from Chroma, but I have provided a list of shaders that each Chroma shader uses in case they are cross-compatible.
- If I didn't list a shader, I did not find any keywords for that shader.

### Stuff to keep in mind
- I have not tested every keyword listed here.
- These are most likely just the defaults used by the Chroma material.
- Some keywords were added in later versions of the game.

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

# Keywords provided by Chroma 
- [Standard](README.md#SimpleLit)
- [OpaqueLight](README.md#OpaqueNeonLight)
- [TransparentLight](README.md#TransparentNeonLight)
- [BaseWater](README.md#WaterLit)


## Standard
`"DIFFUSE", "ENABLE_DIFFUSE", "ENABLE_FOG", "ENABLE_HEIGHT_FOG", "ENABLE_SPECULAR", "FOG", "HEIGHT_FOG", "REFLECTION_PROBE_BOX_PROJECTION", "SPECULAR", "_EMISSION", "_ENABLE_FOG_TINT", "_RIMLIGHT_NONE"`

Added in update 1.30:
`"_ACES_APPROACH_AFTER_EMISSIVE", "_DECALBLEND_ALPHABLEND", "_DISSOLVEAXIS_LOCALX", "_EMISSIONCOLORTYPE_FLAT", "EMISSIONTEXTURE_NONE", "_ROTATE_UV_NONE", "_VERTEXMODE_NONE", "WHITEBOOSTTYPE_NONE", "ZWRITE_ON"`

## OpaqueLight
`"DIFFUSE", "ENABLE_BLUE_NOISE", "ENABLE_DIFFUSE", "ENABLE_HEIGHT_FOG", "ENABLE_LIGHTNING", "USE_COLOR_FOG"`

## TransparentLight
`"ENABLE_HEIGHT_FOG", "MULTIPLY_COLOR_WITH_ALPHA", "_ENABLE_MAIN_EFFECT_WHITE_BOOST"`


## BaseWater
`"FOG", "HEIGHT_FOG", "INVERT_RIMLIGHT", "MASK_RED_IS_ALPHA", "NOISE_DITHERING", "NORMAL_MAP", "REFLECTION_PROBE", "REFLECTION_PROBE_BOX_PROJECTION", "_DECALBLEND_ALPHABLEND", "_DISSOLVEAXIS_LOCALX", "_EMISSIONCOLORTYPE_FLAT", "_EMISSIONTEXTURE_NONE", "_RIMLIGHT_NONE", "_ROTATE_UV_NONE", "_VERTEXMODE_NONE", "_WHITEBOOSTTYPE_NONE", "_ZWRITE_ON"`
