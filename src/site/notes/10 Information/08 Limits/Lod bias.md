---
{"dg-publish":true,"permalink":"/10-information/08-limits/lod-bias/","created":"2024-04-06T15:59:08.964+07:00","updated":"2024-05-26T14:05:02.445+07:00"}
---

```csharp
// normalizedDrawDistance is the nearby draw distance (0 to 1)
QualitySettings.lodBias = 2f + normalizedDrawDistance * 3f + Mathf.Clamp(Provider.preferenceData.Graphics.LOD_Bias, 0f, 5f);
```
* Custom lod bias is limited to 0 and 5
* Default LOD bias 1
* Final lod bias ranges from 2 to 10
* **Lod bias adds onto the in-game value**
---
Source: [SDG.Unturned/GraphicsSettings.cs](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/4559b157f74267d2921f195444d13de7de4febe7/Assembly-CSharp/SDG.Unturned/GraphicsSettings.cs) 
#lod-bias #lod #performance