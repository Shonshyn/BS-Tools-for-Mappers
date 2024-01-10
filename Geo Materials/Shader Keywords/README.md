# Info
Here is where I will list information regarding what I figure out about shader keywords as I mess around with them over time. 

### Stuff to keep in mind
- I know nothing about materials, shaders, and shader keywords.
- I know VERY little about Unity.
- I got these keywords from like 100 different sources from within the game so I don't know how many of these are valid keywords.
- I have not tested every keyword listed here.

### Shader Name Conversion
- I will be listing these keywords under the shader I believe it will work for.
- The shader names I will use are the ones listed in Unity that get put on geo, not the shader names from Chroma as I suspect the one listed by Unity is the important one.
- Here I will have a list of what shader each Chroma shader uses:
  ```
  Standard = SimpleLit
  OpaqueLight = OpaqueNeonLight
  TransparentLight = TransparentNeonLight
  BaseWater = SimpleLit
  BillieWater = WaterLit
  BTSPillar = SimpleLit
  InterscopeConcrete =
  InterscopeCar = SimpleLit
  WaterfallMirror = Mirror
  ```

# Shader List 
This is a list of all shaders currently used by Chroma. (These shaders are the ones listed by the game object your geo has created, not the shader you set in the map materials.)
- SimpleLit
- OpaqueNeonLight
- TransparentNeonLight
- WaterLit
- Mirror
