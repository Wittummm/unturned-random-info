---
{"dg-publish":true,"permalink":"/10-information/00-assets/physics-material-extension-asset/","created":"2024-04-09T21:07:47.915+07:00","updated":"2024-04-09T21:57:27.747+07:00"}
---

```csharp
baseRef = data.ParseStruct<AssetReference<PhysicsMaterialAsset>>("Base");
```
`PhysicsMaterialExtensionAsset` assets has a `Base` property. The Asset Pointer specifies the material asset to replace/extend. 

Source:
[SDG.Unturned/PhysicsMaterialExtensionAsset.cs Line 14](https://github.com/Unturned-Datamining/Unturned-Datamining/blob/4559b157f74267d2921f195444d13de7de4febe7/Assembly-CSharp/SDG.Unturned/PhysicsMaterialExtensionAsset.cs#L14)
#asset-class 