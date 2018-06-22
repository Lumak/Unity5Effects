Unity5 Effects
============

Effect storage for Unity 5.  
If you import this package, you can use it as it is: [IstEffects.unitypackage](https://github.com/i-saint/Unity5Effects/raw/master/Packages/IstEffects.unitypackage)  
Many assume that the rendering pass is deferred. Also, it is more desirable for the camera to be in HDR mode.

## Temporal Screen Space Reflections
![alt text](doc/ScreenSpaceReflections.jpg)  
Screen space reflection.  
Mr. kode80 has released [something similar](https://github.com/kode80/kode80SSR) but there is a disadvantage that the algorithm is different from that there is a slight afterimage, but overwhelmingly fast and the quality does not get caught.  
If you are interested in implementation details, please also read [this article](http://i-saint.hatenablog.com/entry/2014/12/05/174706). The background of the above screenshot is from Raymarcher [here](https://github.com/i-saint/RaymarchingOnUnity5).

## Screen Space Shadows
![alt text](doc/ScreenSpaceShadows.gif)  
It is a light that can shade by laying out G - Buffer. Besides point light sources, it can handle line light sources.
Most of the lighting process is borrowed from [the sample project of the official CommandBuffer](http://blogs.unity3d.com/2015/02/06/extending-unity-5-rendering-pipeline-command-buffers).

## Screen Space Boolean
![alt text](doc/Boolean.gif)  
Screen space boolean calculation by G-Buffer processing.    
Although there are some problems such as heavy, inability to correctly process shadows, collapsing with complicated three-dimensional intersections, there are quite a bit of impact on the appearance.
If you are interested in implementation details, please also [click here](http://i-saint.hatenablog.com/entry/2014/07/25/001608).  

## Rim Light
![alt text](doc/RimLight.jpg)  
Normal and Camera -> This is a pixel that lightens the shallow part of the pixel position. 

## Water Surface & Caustics Field
![alt text](doc/WaterSurface.jpg)  
Water surface and caustics.  
The surface of the water emulates refraction by re - merging G - Buffer. The caustics is brightened with 3-dimensional noise and appears to be like it.


## Light Particle
![alt text](doc/LightParticle.jpg)  
Particle renderer which treats each grain as Point Light. Extension of MassParticle.  


## Procedural Modeling
![alt text](doc/ProceduralModeling.jpg)  
A substitute that renders a distance function in object space by spheres tracing with the surface of Mesh as the starting point. In the image above, all background objects except Unity are all processed by Cube with pixel shader.


## Metaball
![alt text](doc/Metaball.gif)  
Metaball by Ray Maat. It is perfectly complete with GPU, so it should be much faster than mesh generation by MC method etc.
We have borrowed the soft_min () function announced by Media Molecule for implementation. (This page is recommended because it is a treasure trove of information on the kind of procedural modeling.) In addition, because we are using the function of D3D 11 generation (StructuredBuffer), we choose the environment slightly.


## Temporal SSAO
![alt text](doc/SSAO.jpg)  
It is a temporal SSAO which took measures against afterimages by considering dangerous samples.
Although the noise of the moving part is conspicuous, it is a quality that can not be said to withstand practical use for a moment, but if it is limited to a scene with less movement, you can draw a picture of quality that is close to the standard SSAO speed. It may be useful depending on the situation.
I implemented [this](http://bitsquid.blogspot.jp/2015/09/temporal-reprojection-and-sao.html) as a hint, but the original article is much more advanced implementation. I would like to try out handouts of SSAO which are mentioned in each original article.

### Mosaic Field
![alt text](doc/mosaic.gif)  
Shader that mosaicizes the specified object.

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
