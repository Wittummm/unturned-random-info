---
{"dg-publish":true,"permalink":"/10-information/02-performance/general-optimization-unity/","created":"2024-06-07T13:27:41.344+07:00","updated":"2024-06-09T14:52:28.520+07:00"}
---

#### Textures

**Disable the read/write enabled flag**
The `Read/Write enabled` flag causes a Texture to be kept in CPU memory.
`Read/Write Enabled` is only necessary when manipulating Texture data outside of **Shaders**[](https://docs.unity3d.com/2021.3/Documentation/Manual/Shaders.html)  
[](https://docs.unity3d.com/2021.3/Documentation/Manual/Glossary.html#Shader) and should be avoided whenever possible.

**Disable Mipmaps if possible**
If the image won't be seen far away, mipmaps should be avoided to reduce the size of the image by 1/3.
#### Models

**Disable the Read/Write enabled flag**
The`Read/Write enabled` flag for models operates identically to the one described for Textures. However, it is enabled by default for models.
If the model is not used in a MeshCollider and is not manipulated by **scripts**[](https://docs.unity3d.com/2021.3/Documentation/Manual/CreatingAndUsingScripts.html)  
[](https://docs.unity3d.com/2021.3/Documentation/Manual/Glossary.html#Scripts), disable this flag to save half of the model’s memory.
**Note that static batching requires this to be turned on** 

**Disable rigs on non-character models**
By default, Unity imports a generic rig for non-character models. If the model is not animated via the Animation system, this adds unnecessary overhead to the animation system.

**Use Mesh compression when possible**
Enabling Mesh compression reduces the precision of the model’s data. This can lead to a minor loss of precision, and the side-effects should be checked before publishing.

**Disable unnecessary settings**
By default, Unity enables Shadow casting and receiving, **Light Probe** sampling, **Reflection Probe**, and Motion Vector calculation. They should be disabled when not necessary.

Sources:
[Official Unity Asset Optimizing Guide](https://docs.unity3d.com/2021.3/Documentation/Manual/BestPracticeUnderstandingPerformanceInUnity4.html) 