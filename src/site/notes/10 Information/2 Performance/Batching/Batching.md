---
{"dg-publish":true,"permalink":"/10-information/2-performance/batching/batching/","created":"2024-03-31T21:04:30.053+07:00","updated":"2024-03-31T22:24:33.361+07:00"}
---

## How to
* You can enable batching in your level/map by doing `"Batching_Version": 2` in the map `Config.json` 
* You can exclude your asset from batching by setting `Exclude_From_Level_Batching` to <span style="color:red">true</span> in your asset data file.
## Benefits

* Having fewer materials allows the game to batch assets better reducing drawcalls.
## Details

* [[10 Information/2 Performance/Batching/Commands\|Related Commands]]
* [[10 Information/2 Performance/Batching/Requirements for batching\|Requirements for batching]]

#### Sources
[Official Documentation: Level batching](https://docs.smartlydressedgames.com/en/stable/mapping/level-batching.html) 