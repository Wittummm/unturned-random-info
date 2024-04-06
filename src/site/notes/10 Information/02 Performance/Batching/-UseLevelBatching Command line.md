---
{"dg-publish":true,"permalink":"/10-information/02-performance/batching/use-level-batching-command-line/","created":"2024-04-06T21:41:40.601+07:00","updated":"2024-04-06T21:45:48.905+07:00"}
---

```csharp
shouldUseLevelBatching = (!clUseLevelBatching.hasValue || clUseLevelBatching.value) ...
```
- Set `-UseLevelBatching` as `true` → `true`
- Does not set `-UseLevelBatching` → `true`
- Set `UseLevelBatching` as `false` → `false` = **only useful one** 

Source: [SDG.Unturned/Level.cs](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/linux-client-preview/Assembly-CSharp/SDG.Unturned/Level.cs)
#commands #batching #performance 