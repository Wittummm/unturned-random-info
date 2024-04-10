---
{"dg-publish":true,"permalink":"/10-information/08-limits/manual-culling-volume-bias/","created":"2024-04-06T19:26:31.703+07:00","updated":"2024-04-10T14:19:38.070+07:00"}
---

```csharp
// CullingVolume.cs
cullDistance = 64f * targetLevelObject.asset.lodBias;
```
```csharp
// ObjectAsset.cs
lodBias = data.ParseFloat("LOD_Bias");
if (lodBias < 0.01f)
{
    lodBias = 1f;
}    
```
Note that the keys related mainly `LOD` and `LOD_Bias`  are badly named as these parameters relates to **culling** not *level of detail*. 
* **Culling distance is multiplied by the bias**
* **Culling distance ranges from 0.64 to infinity** 
--- 
Sources:
* [SDG.Unturned/CullingVolume.cs; Line 124 ](https://github.com/Unturned-Datamining/Unturned-Datamining/blob/4559b157f74267d2921f195444d13de7de4febe7/Assembly-CSharp/SDG.Unturned/CullingVolume.cs#L124) 
* [SDG.Unturned/ObjectAsset.cs](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/linux-client-preview/Assembly-CSharp/SDG.Unturned/ObjectAsset.cs) 

#culling-bias #performance #culling #manual-culling 