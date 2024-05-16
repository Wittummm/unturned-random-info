---
{"dg-publish":true,"permalink":"/10-information/00-assets/using-player-spot-light-config-in-glasses-asset/","created":"2024-05-16T14:21:47.747+07:00","updated":"2024-05-16T14:24:45.643+07:00"}
---


``` csharp
if (vision == ELightingVision.HEADLAMP)
    {
        lightConfig = new PlayerSpotLightConfig(data);
    }
```
Setting `Vision` to `Headlamp` in the glasses asset definition file allows `PlayerSpotLightConfig`'s properties to be used.

Further reading:
[How to use PlayerSpotLightConfig](https://unturned-random-info.vercel.app/10-information/00-assets/how-to-use-player-spot-light-config/) 

---
Sources:
ItemGlassesAsset.cs

#glasses #playerspotlightconfig 