---
{"dg-publish":true,"permalink":"/10-information/02-performance/gpu-instancing/","created":"2024-06-02T13:01:16.608+07:00","updated":"2024-06-09T14:35:49.868+07:00"}
---

Gpu instancing in Unturned does work but unity already auto batches nearby meshes. If you are sure that your object will be used a lot then enable Gpu Instancing.

Requirements:
- A [MeshRenderer](https://docs.unity3d.com/Manual/class-MeshRenderer.html) component

**VERY Important Note**:
> The threshold at which inefficiencies begin depends on the GPU, but as a general rule, don’t use GPU instancing for meshes that have fewer than 256 vertices.

Then cumulative vertex count of all the instances of the target mesh should be more than 256 vertices. So for a lot of meshes in Unturned, you wouldn't use GPU instancing on.

Cases where you *might* want to use GPU instancing:
- Most buildings
- Some high poly assets

Sources: 
[Unity Manual For Gpu Instancing](https://docs.unity3d.com/Manual/GPUInstancing.html) 
[Unturned Support](https://support.smartlydressedgames.com/hc/en-us/articles/13182728322452-Should-material-GPU-instancing-be-enabled-in-Unity) 