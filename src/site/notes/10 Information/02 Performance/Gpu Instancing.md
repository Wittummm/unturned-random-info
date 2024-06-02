---
{"dg-publish":true,"permalink":"/10-information/02-performance/gpu-instancing/","created":"2024-06-02T13:01:16.608+07:00","updated":"2024-06-02T13:10:18.804+07:00"}
---

Gpu instancing in Unturned does work but unity already auto batches nearby meshes. If you are sure that your object will be used a lot then enable Gpu Instancing.

Requirements:
- A [MeshRenderer](https://docs.unity3d.com/Manual/class-MeshRenderer.html) component

**VERY Important Note**:
> The threshold at which inefficiencies begin depends on the GPU, but as a general rule, don’t use GPU instancing for meshes that have fewer than 256 vertices.

So you basically won't ever use gpu instancing for any meshes as Unturned meshes do not have a lot of geometry  

Sources: 
[Unity Manual For Gpu Instancing](https://docs.unity3d.com/Manual/GPUInstancing.html) 
[Unturned Support](https://support.smartlydressedgames.com/hc/en-us/articles/13182728322452-Should-material-GPU-instancing-be-enabled-in-Unity) 