---
{"dg-publish":true,"permalink":"/10-information/00-assets/how-unturned-knows-what-asset-type-an-asset-is-v1/","created":"2024-06-14T14:13:12.242+07:00","updated":"2024-06-14T14:17:12.384+07:00"}
---

Version 1 is the confusing one, version 2 is quite simple as it is separated into `Metadata.Type` which states the AssetType and `Asset.Type` is the Asset's type.

The `Type` is badly designed as it has 2 uses: the AssetType("ItemAsset") itself and the Asset's type("Large"). 

#### Examples
`Type Vehicle` → refers to `VehicleAsset`
`Type Large` → refers to an `ObjectAsset` that is large

---
Sources:
None?(maybe official docs)
My brain + discord questions :>
