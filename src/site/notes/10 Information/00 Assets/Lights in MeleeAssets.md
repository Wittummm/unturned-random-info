---
{"dg-publish":true,"permalink":"/10-information/00-assets/lights-in-melee-assets/","created":"2024-05-16T14:19:54.406+07:00","updated":"2024-05-16T14:21:28.910+07:00"}
---

`firstLightHook = base.player.equipment.firstModel.Find("Model_0").Find("Light");`
`Transform transform = firstLightHook.Find("Light");`

There needs to be a `Model_0/Light/Light` object with light component

---
Sources:
[UseableMelee.cs Line 712](https://github.com/Unturned-Datamining/Unturned-Datamining/blob/faa74e5dfb140c4cd77b5ce098de4338d50e839a/Assembly-CSharp/SDG.Unturned/UseableMelee.cs#L712) 
#light #melee