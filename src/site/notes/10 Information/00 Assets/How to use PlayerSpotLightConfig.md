---
{"dg-publish":true,"permalink":"/10-information/00-assets/how-to-use-player-spot-light-config/","created":"2024-05-15T13:36:49.893+07:00","updated":"2024-05-15T13:46:00.549+07:00"}
---

```csharp
_isLight = data.ContainsKey("Light"); 
if (isLight) // Checks if the Light flag in the file
    {
        lightConfig = new PlayerSpotLightConfig(data); // if so loads the light config properties from the file
    }
```
When the `Light` flag is in the asset definition file, Unturned searches for the properties ` SpotLight_Enabled`, `SpotLight_Range`, etc of the `PlayerSpotLightConfig`

```q
...
"Light"

"SpotLight_Enabled" "true"
"SpotLight_Range" "16"
"SpotLight_Angle" "50"
"SpotLight_Intensity" "0.7"
...
```

---
Extra reading:
[Official documentation for PlayerSpotlightConfig](https://docs.smartlydressedgames.com/en/stable/data/struct/playerspotlightconfig.html#playerspotlightconfig) 

Sources:
[PlayerSpotlightConfig.cs](https://github.com/Unturned-Datamining/Unturned-Datamining/blob/faa74e5dfb140c4cd77b5ce098de4338d50e839a/Assembly-CSharp/SDG.Unturned/ItemMeleeAsset.cs#L95) 
#playerspotlightconfig #example 