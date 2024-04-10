---
{"dg-publish":true,"permalink":"/10-information/08-limits/inconclusive-manual-object-culling/","created":"2024-04-10T14:17:06.850+07:00","updated":"2024-04-10T14:21:06.149+07:00"}
---

```csharp
// CullingVolume.cs
volume.cullDistance = Mathf.Clamp(value, 1f, ObjectManager.OBJECT_REGIONS * Regions.REGION_SIZE);
```
```csharp
// Regions.cs
public static readonly byte REGION_SIZE = 128;
```
```csharp
// ObjectManagers.cs
public static readonly byte OBJECT_REGIONS = 2;
```
Inconclusive, this seems to only clamp the **visual** in-editor value to be clamped to 1 and 256
---
Sources:
* [SDG.Unturned/Regions.cs](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/4559b157f74267d2921f195444d13de7de4febe7/Assembly-CSharp/SDG.Unturned/Regions.cs) 
* [SDG.Unturned/ObjectManager.cs Line 14](https://github.com/Unturned-Datamining/Unturned-Datamining/blob/4559b157f74267d2921f195444d13de7de4febe7/Assembly-CSharp/SDG.Unturned/ObjectManager.cs#L14) 
* [SDG.Unturned/CullingVolume.cs; Line 124 ](https://github.com/Unturned-Datamining/Unturned-Datamining/blob/4559b157f74267d2921f195444d13de7de4febe7/Assembly-CSharp/SDG.Unturned/CullingVolume.cs#L124) 
#inconclusive #manual-culling