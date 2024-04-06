---
{"dg-publish":true,"permalink":"/10-information/08-limits/lod-bias/","created":"2024-04-06T15:59:08.964+07:00","updated":"2024-04-06T20:51:44.592+07:00"}
---

```csharp
// normalizedDrawDistance is the nearby draw distance (0 to 1)
QualitySettings.lodBias = 2f + normalizedDrawDistance * 3f + Mathf.Clamp(Provider.preferenceData.Graphics.LOD_Bias, 0f, 5f);
```
* Custom lod bias is limited to 0 and 5
* Default LOD bias 0

* Final lod bias ranges from 2 to 10
* **Lod bias adds onto the in-game value**
```math

2 + 0 * 3 + 0 ##Lowest
2 + 1 * 3 + 0 ########
2 + 0 * 3 + 5 ########     
2 + 1 * 3 + 5 #Highest
```

Source: [SDG.Unturned/GraphicsSettings.cs](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/4559b157f74267d2921f195444d13de7de4febe7/Assembly-CSharp/SDG.Unturned/GraphicsSettings.cs) 