---
{"dg-publish":true,"permalink":"/10-information/08-limits/far-clip-distance-render-distance/","created":"2024-04-06T16:02:31.419+07:00","updated":"2024-04-06T20:51:57.624+07:00"}
---

```csharp
float num = (0.3f + NormalizedFarClipDistance * 0.7f) * 2048f; // 614.4 - 2048(0 - 1)
if (clFarClipDistance.hasValue)
{
    num = Mathf.Clamp(clFarClipDistance.value, 16f, 2048f);
}
```
- `num` is the final *FarClipPlane* value
- `clFarClipDistance` is the command line "-FarClipDistance" value
**The in-game render distance slider ranges from 614.4 to 2048** 

Source: [SDG.Unturned/GraphicsSettings.cs](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/4559b157f74267d2921f195444d13de7de4febe7/Assembly-CSharp/SDG.Unturned/GraphicsSettings.cs) 