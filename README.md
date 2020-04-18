# DeepAo
[DeepAO: Efficient Screen Space Ambient Occlusion Generation via Deep Network](https://ieeexplore.ieee.org/document/9052668)

## Dataset Sample Visualization
![Image text](https://raw.githubusercontent.com/dokju15692002156/DeepAo/master/Dataset%20Demo/DATASET.png)

## Dataset Generation Pipline  
We use 3dsMax with Vray engine to generate our dataset. Our AO dataset contain Ao map and corresponding Depth map and Normal map. You can make your own dataset by following these steps:   
  1.Make your own 3d scene, you can get 3D material from [Free3d](https://free3d.com/zh/?__cf_chl_captcha_tk__=de16bd0727a079082c4c7c81bae2e15d16fb5fb9-1587184515-0-AbhP8f7FreGGyussw_P5ZZT-4NMkKXy6WY4tHAbts9CK-Xi-X-cwEBMTpZwo0n099A7FZiqv1OwzTvXf9oAs5swy0eG-ZHeH66MprcCtesmypmZ1MmIwWlPJc5iQMfc21AhD9xhd3zUUCBzDK37QHM92Xju3xRpwpLcpDBmldcD2RtRKVQVX6InO3Md9_lq4FTqAaYfJgE5az3oQZI5r3IDJ-rUMoQ8E3XpJmh4uVohqqZ_Spj7hgbLFVuJrSjypJFiXuyZVic4nXMjTfZgEYpzzUPrhQH_B8v03KCtVtNu7U_Y49t0BkSLQZOPL5rhu8DOUTj4lkMqddFf6uYzA-o1g2T0LxTeQQC3UV7viUMyFdCGH2CgZ8GE41CfAy1aLKg).  
  2.Configure the Vray engine.  
      + AO map: Configure the Vray engine according to the instructions [here](http://www.laurenscorijn.com/articles/ambient-occlusion-baking)  for bake Ambient Occlusion Map(Method 4 or 5, It depends on your needs).  
      + Position map: VRaySamplerInfo is recommended instead of VrayZDepth, because the depth value obtained by VrayZDepth is nonlinear.You can get the xyz coordinates of each point from VRaySamplerInfo. Our experiment only use Z coordinates(Z depth).   
      + Normal map: You can use VRaySamplerInfo or VRayNormals, VRaySamplerInfo can generate normal in camera space and world space. VRayNormals can only generate normal in camera space. Our experiment use normal in camera space.  
   3.Planned shooting path and bind camera.    
   4.Use Batch Render to render the scene.  
   
