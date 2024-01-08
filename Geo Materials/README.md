# Info

All screenshots are on the Billie environment with all of the env being removed except for `BigSmokePS` to show whether or not the material will be "corrupted" on the envs that do that to geo.

Anytime I mention "directional lights" I'm referring to the `DirectionalLight` game objects in the env. (Ex: `DirectionalLightFront`, `DirectionalLightBack`, `DirectionalLightLeft`, and `DirectionalLightRight`) 

Example of what I'm calling "corrupted": 
```
map.geoMaterials["DefaultConcrete"] = {
  shader: "InterscopeConcrete",
  color: [1,1,1,1]
}
```
(https://github.com/Shonshyn/BS-Tools-for-Mappers/blob/main/Geo%20Materials/corrupted%20example.png) 

If a screenshot has any other env pieces/geo/game objects, it was done to show a certain type of effect that the material will have. For example, some shader keywords will cause any smoke to not be visible from behind the geo. In these cases, I likely threw in the `Clouds` env piece or something else to better demonstrate that.

All screenshots also have the environment fog unchanged from the default values unless specified otherwise. 
All screenshots also have the geo and env rotated a bit to show how a material will react to directional lights. 

All code snippets will have `map` set the output difficulty. Here's an example of that, with `ExpertPlusLawless.dat` being the input and `ExpertPlusStandard.dat` being the output:
```
const map = new Difficulty("ExpertPlusLawless.dat", "ExpertPlusStandard.dat");
```
You can change it to whatever you want but the `map` in the material code will have to match whatever you chose for your output difficulty.

If a material does have `color:` set, then it cannot be colored by the material. However, it still could be colored by the lightmap, directional lights

# Material List

## Wood/Stone Material
```
map.geoMaterials["WoodMat"] = {
  shader: "InterscopeConcrete",
  color: [0.5, 0.368, 0.36, 1],
  shaderKeywords: ["DIFFUSE", "DIRT", "FOG", "REFLECTION_PROBE_BOX_PROJECTION"]
}
```
![Wood Image](https://github.com/Shonshyn/BS-Tools-for-Mappers/blob/main/Geo%20Materials/wood.png)
![Wood Plank](https://github.com/Shonshyn/BS-Tools-for-Mappers/blob/main/Geo%20Materials/wood%20plank.png)
![Stone/Rock](https://github.com/Shonshyn/BS-Tools-for-Mappers/blob/main/Geo%20Materials/stone%20rock.png)

## Crystal/Glass Material
```
map.geoMaterials["CrystalMat"] = {
  shader: "TransparentLight",
  shaderKeywords: [
    "REFLECTION_PROBE"
  ]
};
```
![Crystal Image](https://github.com/Shonshyn/BS-Tools-for-Mappers/blob/main/Geo%20Materials/crystal.png)
