# Info

All screenshots are on the Billie environment to show whether or not the material will be "corrupted" on the environments that do that to geo.

All code snippets will have `map` set the output difficulty. Here's an example of that, with `ExpertPlusLawless.dat` being the input and `ExpertPlusStandard.dat` being the output:
```
const map = new Difficulty("ExpertPlusLawless.dat", "ExpertPlusStandard.dat");
```
You can change it to whatever you want but the `map` in the material code will have to match whatever you chose for your output difficulty.

### Material List

# Wood/Stone Material
![Wood Image](https://github.com/Shonshyn/BS-Tools-for-Mappers/blob/main/Geo%20Materials/wood.png)
```
map.geoMaterials["WoodMat"] = {
  shader: "InterscopeConcrete",
  color: [0.5, 0.368, 0.36, 1],
  shaderKeywords: ["DIFFUSE", "DIRT", "FOG", "REFLECTION_PROBE_BOX_PROJECTION"]
}
```
