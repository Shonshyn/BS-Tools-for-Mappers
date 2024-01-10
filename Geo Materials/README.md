# Info

### Remapper Integration
- Aurellis (Aureliona1) added a `material.ts` script which is supposed to allow you to use the materials listed here as a constant in Remapper if you place the `material.ts` in the map folder, but I have not personally tested this yet.
- Can be used simply as
  ```typescript
  import { MaterialPresets } from "./materials.ts";

  map.geoMaterials["Dirt"] = MaterialPresets.Dirt;

  // Or you would like to modify the material slightly.

  const dirtMat = MaterialPresets.Dirt;
  dirtMat.color = [1, 1, 0, 1];
  map.geoMaterials["Dirt"] = dirtMat;
  ```

### My Vocab
- Anytime I mention "env pieces" I'm referring to game objects that are loaded in when a level is loaded, which can be affected with Environment Enhancement. 

- Anytime I mention "directional lights" I'm referring to the `DirectionalLight` game objects in the env. For example, on Billie there are `DirectionalLightFront`, `DirectionalLightBack`, `DirectionalLightLeft`, and `DirectionalLightRight` under `DayAndNight/Day` and `DayAndNight/Night`

### Details
- All screenshots use the Billie environment with all of the env pieces being removed, except for `BigSmokePS`, to show whether or not the material will be "corrupted" on the envs that do that to geo. (See ["Corruption"](README.md#corruption))

   - If a screenshot has any other env pieces/geo/game objects, it was done to show a certain type of effect that the material will have. For example, some shader keywords will cause any smoke to not be visible from behind the geo. In these cases, I likely threw in the `Clouds` env piece or something else to better demonstrate that.
 
- All screenshots have the environment fog unchanged from the default values unless specified otherwise. 

- All screenshots have the geo and env rotated a bit to show how a material will react to directional lights. 

- In any screenshots with the background colored, every light for the env was set to either red or blue and the lights for geo were set to green to show how the lightmaps/reflection probes would affect the material.

- All code snippets will use `map` as the output. Here's an example of that, with `ExpertPlusLawless.dat` being the input and `ExpertPlusStandard.dat` being the output:
   ```typescript
   const map = new Difficulty("ExpertPlusLawless.dat", "ExpertPlusStandard.dat");
   ```
- You can change it to whatever you want but the `map` in the material code will have to match whatever you chose for your output difficulty.

- If a material does not have `color` set, then it cannot be colored by the material. However, it still could be colored by: the lightmap, directional lights, or by lighting the geo itself, if supported. (See [Light-able Shaders](README.md#the-three-light-able-shaders-that-i-know-of))

### "Corruption"
The environments I know of currently that "corrupt" some materials are Billie, Interscope, and Linkin.

I believe the corruption is caused by the light maps in some materials, as removing the lightmap or changing lightmaps fixes this problem. I could be wrong on this though.

These materials will be corrupted if these environments are in use, or even loaded *before* playing the map even if the environment you use is not one of them. So, it is best to not use them.

Example of what I'm calling "corrupted": 
```typescript
map.geoMaterials["DefaultConcrete"] = {
  shader: "InterscopeConcrete",
  color: [1,1,1,1]
}
```
[Corrupted Example Image](https://github.com/Shonshyn/BS-Tools-for-Mappers/blob/main/Geo%20Materials/Example%20Images/corrupted%20example1.png) 

### The Three Light-able Shaders (that I know of)
Everybody knows about `TransparentLight` and `OpaqueLight`, but not a lot of people know that `BillieWater` contains all the necessary stuff to act as a light, and can be lit with the right shader keywords (or lack thereof).
A lot of people also don't know that the three shaders also look different from one another when lit.
All geo in the first three screenshots has `bloomFogIntensityMultiplier` set to zero, with the last having bloom untouched.

Unlit:
![Unlit Image](Example%20Images/unlitlights.png)
Lit:
![Lit Image](Example%20Images/litlights.png)
Lit, but lights are set to [0,0,0,0]:
![Black Lit Image](Example%20Images/blacklights.png)
Lit with bloom:
![Lit Bloom Image](Example%20Images/litlightsbloom.png)



Material on the left:
```typescript
map.geoMaterials["DefaultOL"] = {
  shader: "OpaqueLight"
}
```

Material on the right:
```typescript
map.geoMaterials["DefaultTL"] = {
  shader: "TransparentLight"
}
```

Material on the top:
```typescript
map.geoMaterials["GlowlessLight"] = {
  shader: "BillieWater",
  shaderKeywords: []
}
```

# Material List 
[Fixed Concrete](README.md#fixed-concrete)

[Dirt/Wood/Stone](README.md#dirt)

[Blurry Metal](README.md#blurry-metal)

[Shiny Metal](README.md#shiny-metal)

[Crystal/Glass](README.md#crystalglass)

[Fog Light](README.md#fog-light)

[Grid/Swirly Circle/Swirly Ball](README.md#gridswirly-circleswirly-ball)

[Invisible](README.md#invisible)

[Slightly Reflective](README.md#slightly-reflective)

[Blurry Mirror](README.md#blurry-mirror)

[Shiny Mirror](README.md#shiny-mirror)



## Fixed Concrete
I tried to match the default `InterscopeConcrete` shader as much as possible, but I removed the lightmap to fix the "corruption". ~~This way of doing it also removes the ability to color the material, but I might try to find a way to fix that later.~~ Added `"DIFFUSE"` to the "FixedConcrete" material which allows it to be colored again. :)

Comparison:
![Concrete Comparison Image](Example%20Images/coloredconcrete.png)


Material on the left:
```typescript
map.geoMaterials["DefaultConcrete"] = {
  shader: "InterscopeConcrete",
  color: [0, 1, 0, 1]
}
```

Material on the right:
```typescript
map.geoMaterials["FixedConcrete"] = {
  shader: "InterscopeConcrete",
  color: [0, 1, 0, 1],
  shaderKeywords: ["DIFFUSE", "DIRT", "ENABLE_DIFFUSE", "ENABLE_DIRT", "ENABLE_DIRT_DETAIL", "ENABLE_FOG", "ENABLE_GROUND_FADE", "ENABLE_SPECULAR", "ENABLE_VERTEXT_COLOR", "FOG", "NOISE_DITHERING", "REFLECTION_PROBE", "REFLECTION_PROBE_BOX_PROJECTION", "REFLECTION_PROBE_BOX_PROJECTION_OFFSET", "_EMISSION", "_ENABLE_FOG_TINT", "_RIMLIGHT_NONE"]
}
```

## Dirt
Can also be used for grass, snow, wood, stone, rocks, and really anything that needs texture but doesn't need to be shiny/reflective.
```typescript
map.geoMaterials["DirtMat"] = {
  shader: "InterscopeConcrete",
  color: [0.5, 0.368, 0.36, 1],
  shaderKeywords: ["DIFFUSE", "DIRT", "FOG", "REFLECTION_PROBE_BOX_PROJECTION"]
}
```
![Wood Image](Example%20Images/wood.png)
![Wood Plank](Example%20Images/wood%20plank.png)
![Stone/Rock](Example%20Images/stone%20rock.png)

## Blurry Metal

NOTE: Material color will only be visible on the sides affected by directional lights.

If you do not need the material to be colorable, remove `"DIFFUSE"` and it will appear a little more reflective.
You can also remove `"REFLECTION_PROBE_BOX_PROJECTION"` to make it a 2d reflection instead of a weird 3d-ish reflection.
```typescript
map.geoMaterials["MetalMat1"] = {
   shader: "InterscopeConcrete",
   color: [0, 1, 0, 1],
   shaderKeywords: [
      "DIRT",
      "DIFFUSE",
      "FOG",
      "REFLECTION_PROBE",
      "REFLECTION_PROBE_BOX_PROJECTION",
      "REFLECTION_PROBE_BOX_PROJECTION_OFFSET"
   ]
}
```
This screenshot was taken from a different angle to better show the reflection.
![Blurry Metal Image](Example%20Images/blurrymetal.png)

## Shiny Metal

NOTE: Material color will only be visible on the sides affected by directional lights.

If you do not need the material to be colorable, remove `"DIFFUSE"` and it will appear a little more reflective.
You can also remove `"REFLECTION_PROBE_BOX_PROJECTION"` to make it a 2d reflection instead of a weird 3d-ish reflection.
```typescript
map.geoMaterials["MetalMat2"] = {
   shader: "InterscopeCar",
   color: [0, 1, 0, 1],
   shaderKeywords: [
      "DIRT",
      "DIFFUSE",
      "FOG",
      "REFLECTION_PROBE",
      "REFLECTION_PROBE_BOX_PROJECTION",
      "REFLECTION_PROBE_BOX_PROJECTION_OFFSET"
   ]
}
```
![Shiny Metal Image](Example%20Images/shinymetal.png)

## Crystal/Glass
```typescript
map.geoMaterials["CrystalMat"] = {
  shader: "TransparentLight",
  shaderKeywords: [
    "REFLECTION_PROBE"
  ]
};
```
Unlit:
![Crystal Image](Example%20Images/crystal.png)
![Crystal Image](Example%20Images/crystalunlit.png)
Lit:
![Crystal Lit](Example%20Images/crystallit.png) 

## Fog Light
Light dissolves in fog, the bloom from `TubeBloomPrePassLight` component is still visible though. Can also be used without being lit to hide some parts of something in the fog, as nothing behind the geo in the fog will be visible.
```typescript
map.geoMaterials["FogMat"] = {
  shader: "OpaqueLight",
  shaderKeywords: ["ENABLE_HEIGHT_FOG"]
}
```
This screenshot has the fog set to these parameters: 
```typescript
components.BloomFogEnvironment = {
  attenuation: 0,
  offset: 0,
  startY: -0.25,
  height: 0
}
```

![Fog Image](Example%20Images/foglight.png)

## Grid/Swirly Circle/Swirly Ball
The grid texture this material uses is the same texture used for mirrors, it's just usually a little hard to see on mirrors because of the reflective nature of a mirror. (also most of the base game mirrors have the texture scaled super tiny)

This material always glows for some reason, it could be possible that the glow can be removed but I haven't figured it out.

Throw it on a sphere and you get some cool swirls. It can also be used to make a cool-looking eyeball, I've discovered.
```typescript
map.geoMaterials["GridMat"] = {
  shader: "WaterfallMirror",
  shaderKeywords: ["ENABLE_DIRT"]
}
```
![Grid Image](Example%20Images/grid.png)

## Invisible
This material is invisible or does not render, or is broken because it doesn't like instancing or something idk. It's a great way to get some collision without using an unlit transparent light.

NOTE: Giving geo a collider WILL block the pause menu controllers from clicking buttons if the geo gets in the way.

This effect also works with the `BillieWater` shader, but I assume using that shader would be slightly more expensive. It could also not matter since the material is invisible, but I wouldn't risk it either way.
```typescript
map.geoMaterials["InvisMat"] = {
  shader: "InterscopeConcrete",
  shaderKeywords: ["INSTANCING_ON"]
}
```
![Invisible Image](Example%20Images/invis.png)

## Slightly Reflective
This material has a VERY subtle reflection to it.

If you do not need the material to be colorable, remove `"DIFFUSE"` and it will appear a little more reflective.
You can also remove `"REFLECTION_PROBE_BOX_PROJECTION"` to make it a 2d reflection instead of a weird 3d-ish reflection.
```typescript
map.geoMaterials["ReflectMat1"] = {
   shader: "BTSPillar",
   color: [0, 1, 0, 1],
   shaderKeywords: [
      "DIFFUSE",
      "FOG",
      "REFLECTION_PROBE",
      "REFLECTION_PROBE_BOX_PROJECTION"
   ]
}
```
![Slightly Reflective Image](Example%20Images/slightreflection.png)

## Blurry Mirror
Not a true mirror, uses the env's reflection probes.

NOTE: Material color will only be visible on the sides affected by directional lights.

If you do not need the material to be colorable, remove `"DIFFUSE"` and it will appear a little more reflective.
You can also remove `"REFLECTION_PROBE_BOX_PROJECTION"` to make it a 2d reflection instead of a weird 3d-ish reflection.
```typescript
map.geoMaterials["ReflectMat2"] = {
   shader: "InterscopeConcrete",
   color: [0, 1, 0, 1],
   shaderKeywords: [
      "DIFFUSE",
      "FOG",
      "REFLECTION_PROBE",
      "REFLECTION_PROBE_BOX_PROJECTION"
   ]
}
```
![Blurry Mirror Image](Example%20Images/blurreflection.png)

## Shiny Mirror
Not a true mirror, uses the env's reflection probes.

NOTE: Material color will only be visible on the sides affected by directional lights.

If you do not need the material to be colorable, remove `"DIFFUSE"` and it will appear a little more reflective.
You can also remove `"REFLECTION_PROBE_BOX_PROJECTION"` to make it a 2d reflection instead of a weird 3d-ish reflection.
```typescript
map.geoMaterials["ReflectMat3"] = {
   shader: "InterscopeCar",
   color: [0, 1, 0, 1],
   shaderKeywords: [
      "DIFFUSE",
      "FOG",
      "REFLECTION_PROBE",
      "REFLECTION_PROBE_BOX_PROJECTION"
   ]
}
```
![Shiny Mirror Image](Example%20Images/shinyreflection.png)

