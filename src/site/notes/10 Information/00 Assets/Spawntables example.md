---
{"dg-publish":true,"permalink":"/10-information/00-assets/spawntables-example/","created":"2024-05-14T20:18:12.386+07:00","updated":"2024-05-14T20:26:12.397+07:00"}
---

```json
"Metadata"
{
	"Guid" "weee woooo booo hooo"
	"Type" "SDG.Unturned.SpawnAsset, ..."
}
"Asset"
{
	"Tables"
	[
	    {
	        // Military Magazine
	        "Guid" "dbfb1d0d11ca438e9dffb95f76e61274"
	        "Weight" "90"
	    }
	    {
	        // Eaglefire
	        "Guid" "b03d581a5c1a490f995f8deba57b0f17"
	        "Weight" "10"
	    }
	]
	"Roots"
	[
		{
			"Guid" "wwwwwwwwwww" // the guid of the spawn table this spawn table should be in
			"Weight" "100"
			"IsOverride" "true" // make default spawns not spawn
		}
	]
}
```

---
(Has not been verified to work)

#spawntable #assets #example