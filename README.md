# DeepAo
[DeepAO: Efficient Screen Space Ambient Occlusion Generation via Deep Network](https://ieeexplore.ieee.org/document/9052668)

## Dataset Sample Visualization
![Image text](https://raw.githubusercontent.com/dokju15692002156/DeepAo/master/img/DATASET.png)

## Dataset Generation Pipline
We use 3dsMax with Vray engine to generate our dataset. Our AO dataset contain Ao map and corresponding Depth map and Normal map. You can make your own dataset by following these steps:
  *AO map: Configure the Vray engine according to the instructions [here](http://www.laurenscorijn.com/articles/ambient-occlusion-baking)  for bake Ambient Occlusion Map(Method 4 or 5, It depends on your needs).
  *Position map: VRaySamplerInfo is recommended instead of VrayZDepth, because the depth value obtained by VrayZDepth is nonlinear.You can get the xyz coordinates of each point from VRaySamplerInfo.
   *Normal map: You can use VRaySamplerInfo or VRayNormals, VRaySamplerInfo can generate normal in camera space and world space. VRayNormals can only generate normal in camera space. Our experiment use normal in camera space.
