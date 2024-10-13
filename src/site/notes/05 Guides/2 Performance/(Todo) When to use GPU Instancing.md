---
{"dg-publish":true,"permalink":"/05-guides/2-performance/todo-when-to-use-gpu-instancing/","created":"2024-10-12T17:52:26.080+07:00","updated":"2024-10-13T20:18:08.078+07:00"}
---

**Requirements**
- Set `Exclude_From_Level_Batching` as `true` 
- Enable GPU Instancing in the shader/material

GPU Instancing should be used on objects that has more than 5 occurrences and more than 256 cumulative vertices. 


---
Sources: 
- [Unity Manual: GPU Instancing](https://docs.unity3d.com/Manual/GPUInstancing.html) 