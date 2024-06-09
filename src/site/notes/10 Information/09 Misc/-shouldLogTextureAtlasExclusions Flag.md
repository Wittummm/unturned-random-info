---
{"dg-publish":true,"permalink":"/10-information/09-misc/should-log-texture-atlas-exclusions-flag/","created":"2024-06-09T15:15:01.313+07:00","updated":"2024-06-09T15:16:48.752+07:00"}
---

```csharp
UnturnedLog.info("Excluding mesh \"" + mesh.name + "\" in renderer \"" + renderer.GetSceneHierarchyPath() + "\" from level batching because it is not CPU-readable");
```

This flag actually also logs why meshes are not eligible for (static) batching.

Sources:
[LevelBatching.cs](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/linux-client-preview/Assembly-CSharp/SDG.Unturned/LevelBatching.cs)
