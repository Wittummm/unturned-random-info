---
{"dg-publish":true,"permalink":"/10-information/00-assets/documentation/vehicle-assets/","created":"2024-09-06T20:13:05.366+07:00","updated":"2024-09-08T14:11:09.851+07:00"}
---

Deprecated properties are not listed
### List of properties, categorized
##### Asset Configuration
| Property                 | Type | Default | Description                                                                     |
| ------------------------ | ---- | ------- | ------------------------------------------------------------------------------- |
| Bypass_Hash_Verification | flag | -       | "Disable hash verification check, and allow for mismatched files." (??, verify) |
##### Bicycles
| Property           | Type    | Default | Description           |
| ------------------ | ------- | ------- | --------------------- |
| Bicycle            | flag    | -       | Use bicycle animation |
| Bicycle_Anim_Speed | float32 | 0       | -                     |
##### Visuals
| Property                        | Type                                                                                                                                                                                  | Default | Description                                                   |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | ------------------------------------------------------------- |
| AdditionalTransparentSections   | Array[string]                                                                                                                                                                         |         | -                                                             |
| DefaultPaintColor_Configuration | <small>Dict([VehicleRandomPaintColorConfiguration](https://docs.smartlydressedgames.com/en/latest/assets/vehicle-asset.html#vehiclerandompaintcolorconfiguration-dictionary))</small> |         | When `DefaultPaintColor_Mode` is `RandomHueOrGrayscale`       |
| DefaultPaintColor_Mode          | [EVehicleDefaultPaintColorMode](https://docs.smartlydressedgames.com/en/latest/assets/vehicle-asset.html#evehicledefaultpaintcolormode)                                               |         | Overrides how paint colors should be picked                   |
| DefaultPaintColors              | Array[color]                                                                                                                                                                          |         | When configured, auto sets `DefaultPaintColor_Mode` to `List` |
##### Building
| Property                 | Type                                                                                                                                                  | Default Value |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| Buildable_Placement_Rule | [EVehicleBuildablePlacementRule](https://docs.smartlydressedgames.com/en/latest/assets/vehicle-asset.html#evehiclebuildableplacementrule-enumeration) | `None`        |
##### Camera
| Property             | Type    | Default |                                                                                  |
| -------------------- | ------- | ------- | -------------------------------------------------------------------------------- |
| Cam_Driver_Offset    | float32 | 0       | Vertical first person camera offset for driver(adds onto `Cam_Passenger_Offset`) |
| Cam_Follow_Distance  | float32 | 5.5     | -                                                                                |
| Cam_Passenger_Offset | float32 | 0       | Vertical first person camera offset including the driver                         
##### General Vehicle Configuration
| Property                 | Type                                                                                                    | Default | Description |
| ------------------------ | ------------------------------------------------------------------------------------------------------- | ------- | ----------- |
| Can_Be_Locked            | bool                                                                                                    | true    | -           |
| Can_Repair_While_Seated  | bool                                                                                                    | false   | ?(WIP)      |
| Carjack_Force_Multiplier | float32                                                                                                 | 1       | -           |
| Engine                   | [EEngine](https://docs.smartlydressedgames.com/en/latest/assets/vehicle-asset.html#eengine-enumeration) | `Car`   | Engine type |
##### Handling

| Property               | Type    | Default Value | Description                                                                                                                                                   |
| ---------------------- | ------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Center_Of_Mass         | vector3 | -             | Overrides the center of mass, when `Override_Center_Of_Mass` is `true`                                                                                        |
| Brake                  | float32 | -             |                                                                                                                                                               |
| EngineMaxTorque        | float32 | 1             | Multiplier on engine torque output, more details [here](https://docs.smartlydressedgames.com/en/latest/assets/vehicle-asset.html#enginemaxtorque-float32-1-0) |
| EngineRPM_DecreaseRate | float32 | 10,000        | [May](https://docs.smartlydressedgames.com/en/latest/assets/vehicle-asset.html#enginerpm-decreaserate-float32-10000-0) not be useful                          |

###### Air Vehicles
When `Engine` is `Plane`

| Property                | Type    | Default     | Description                               |
| ----------------------- | ------- | ----------- | ----------------------------------------- |
| Air_Steer_Max           | float32 | `Steer_Max` | Angle to turn at max speed, when airborne |
| Air_Steer_Min           | float32 | `Steer_Min` | Angle to turn at min speed, when airborne |
| Air_Turn_Responsiveness | float32 | 2           | -                                         |
##### Battery
| Property                        | Type                                                                                                             | Default                                                                                        | Description                                                                                                                           |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Battery_Burn_Rate               | float32                                                                                                          | 20                                                                                             | Battery per second                                                                                                                    |
| Battery_Charge_Rate             | float32                                                                                                          | 20                                                                                             | Battery per second                                                                                                                    |
| Battery_Powered                 | flag                                                                                                             |                                                                                                | Does not use fuel                                                                                                                     |
| Battery_Spawn_Charge_Multiplier | float32                                                                                                          | 1                                                                                              | \[0 - 1\]                                                                                                                             |
| BatteryMode_Driving             | [EBatteryMode](https://docs.smartlydressedgames.com/en/latest/data/enum/ebatterymode.html#doc-data-ebatterymode) | `Charge`                                                                                       | Battery behavior when driving                                                                                                         |
| BatteryMode_Empty               | [EBatteryMode](https://docs.smartlydressedgames.com/en/latest/data/enum/ebatterymode.html#doc-data-ebatterymode) | `None`                                                                                         | Battery behavior when unoccupied                                                                                                      |
| BatteryMode_Headlights          | [EBatteryMode](https://docs.smartlydressedgames.com/en/latest/data/enum/ebatterymode.html#doc-data-ebatterymode) | `Burn`                                                                                         | Battery behavior when headlights are on                                                                                               |
| BatteryMode_Sirens              | [EBatteryMode](https://docs.smartlydressedgames.com/en/latest/data/enum/ebatterymode.html#doc-data-ebatterymode) | `Burn`                                                                                         | Battery behavior when sirens are on                                                                                                   |
| Can_Steal_Battery               | bool                                                                                                             | true                                                                                           | "Whether or not the vehicle battery can be removed from the vehicle by a player." ?? what player, has to be driver or what            |
| Cannot_Spawn_With_Battery       | flag                                                                                                             | -                                                                                              | -                                                                                                                                     |
| Default_Battery                 | GUID                                                                                                             | <small><small><small><small>`098b13be34a7411db7736b7f866ada69`</small></small></small></small> | "Battery item given to the player when a specific battery hasn’t been manually installed yet." ? like when? when spawn naturally orrr |
|                                 |                                                                                                                  |                                                                                                |                                                                                                                                       |
##### Collisions

| Property            | Type    | Default | Description                                 |
| ------------------- | ------- | ------- | ------------------------------------------- |
| Bumper_Invulnerable | flag    |         | The vehicle cannot be damaged by collisions |
| Bumper_Multiplier   | float32 | 1       | Multiplier for collision sensitivity        |
##### Durability

| Property                         | Type    | Default | Description                                                     |
| -------------------------------- | ------- | ------- | --------------------------------------------------------------- |
| Child_Explosion_Armor_Multiplier | float32 | 0.2     | Multiplier on the damage that buildables on the vehicle receive |
##### Loot/Drops

| Property       | Type   | Default | Description |
| -------------- | ------ | ------- | ----------- |
| Drops_Max      | uint8  | 7       | -           |
| Drops_Min      | uint8  | 3       | -           |
| Drops_Table_ID | uint16 | 962     | -           |
##### Misc

| Property         | Type                                                                                                                                                           | Default  | Description                                                             |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ----------------------------------------------------------------------- |
| EngineSound_Type | [EVehicleEngineSoundType](https://docs.smartlydressedgames.com/en/latest/assets/vehicle-asset.html#doc-assets-vehicle-evehicleenginesoundtype)                 | `Legacy` | How engine sound is controlled                                          |
| EngineSound      | Dict([RpmEngineSoundConfiguration](https://unturned-random-info.vercel.app/10-information/00-assets/documentation/vehicle-assets#RpmEngineSoundConfiguration)) | -        | Used to tune engine soundp when `EngineSound_Type` is `EngineRPMSimple` |
|                  |                                                                                                                                                                |          |                                                                         |
##### RpmEngineSoundConfiguration

| Property   | Type    | Default |
| ---------- | ------- | ------- |
| IdlePitch  | float32 | 0       |
| IdleVolume | float32 | 0       |
| MaxPitch   | float32 | 0       |
| MaxVolume  | float32 | 0       |

#
---
Sources:
[Official Unturned Documentation: Vehicle Assets](https://docs.smartlydressedgames.com/en/latest/assets/vehicle-asset.html) 
#documentation