---
{"dg-publish":true,"permalink":"/10-information/00-assets/how-player-light-config-works/","created":"2024-04-09T20:14:27.859+07:00","updated":"2024-04-09T21:57:47.506+07:00"}
---

```csharp
_isLight = data.ContainsKey("Light"); // same as isLight
if (isLight)
{
    lightConfig = new PlayerSpotLightConfig(data); // Data is the whole Asset Data file(.dat/.asset)
}
```
```csharp
public PlayerSpotLightConfig(DatDictionary data)
    {
        isEnabled = data.ParseBool("SpotLight_Enabled", defaultValue: true);
        range = data.ParseFloat("SpotLight_Range", 64f);
        angle = data.ParseFloat("SpotLight_Angle", 90f);
        intensity = data.ParseFloat("SpotLight_Intensity", 1.3f);
        color = data.LegacyParseColor("SpotLight_Color", new Color32(245, 223, 147, byte.MaxValue));
    }
```
if theres the `Light`  flag in the data file it will search for `SpotLight_Enabled`, `SpotLight_Range`, `SpotLight_Angle`, `SpotLight_Intensity`, `SpotLight_Color` <span style="color:#f5df93">Default color: ██</span>

Sources
[SDG.Unturned/PlayerSpotLightConfig.cs](https://github.com/Unturned-Datamining/Unturned-Datamining/blob/4559b157f74267d2921f195444d13de7de4febe7/Assembly-CSharp/SDG.Unturned/PlayerSpotLightConfig.cs#L34)
SDG.Unturned/ItemMeleeAsset.cs

#property-explaination