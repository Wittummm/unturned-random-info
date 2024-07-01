---
{"dg-publish":true,"permalink":"/10-information/00-assets/how-e-player-temperature-works/","created":"2024-07-01T15:19:12.504+07:00","updated":"2024-07-01T15:23:29.342+07:00"}
---

```
if (ePlayerTemperature == EPlayerTemperature.ACID)
        {
            ePlayerTemperature2 = EPlayerTemperature.ACID;
            if (Provider.isServer && simulation - lastBurn > 10)
            {
                lastBurn = simulation;
                askDamage(10, Vector3.up, EDeathCause.SPIT, ELimb.SPINE, Provider.server, out var _);
            }
        }
        else if (ePlayerTemperature == EPlayerTemperature.BURNING)
        {
            ePlayerTemperature2 = EPlayerTemperature.BURNING;
            if (Provider.isServer && simulation - lastBurn > 10)
            {
                lastBurn = simulation;
                askDamage(10, Vector3.up, EDeathCause.BURNING, ELimb.SPINE, Provider.server, out var _);
            }
            lastWarm = simulation;
            wasWarm = true;
        }
        else if (ePlayerTemperature == EPlayerTemperature.WARM || warmth != 0)
        {
            ePlayerTemperature2 = EPlayerTemperature.WARM;
            lastWarm = simulation;
            wasWarm = true;
        }
        else if (base.player.movement.inSnow && Level.info != null && Level.info.configData.Snow_Affects_Temperature)
        {
            if (base.player.stance.stance == EPlayerStance.SWIM)
            {
                ePlayerTemperature2 = EPlayerTemperature.FREEZING;
                if (Provider.isServer && simulation - lastFreeze > 25)
                {
                    lastFreeze = simulation;
                    byte b = 8;
                    if (base.player.clothing.shirtAsset != null || base.player.clothing.vestAsset != null)
                    {
                        b -= 2;
                    }
                    if (base.player.clothing.pantsAsset != null)
                    {
                        b -= 2;
                    }
                    if (base.player.clothing.hatAsset != null)
                    {
                        b -= 2;
                    }
                    askDamage(b, Vector3.up, EDeathCause.FREEZING, ELimb.SPINE, Provider.server, out var _);
                }
            }
            else if (!wasWarm || (float)(simulation - lastWarm) > 250f * (1f + base.player.skills.mastery(1, 5)))
            {
                if ((base.player.movement.getVehicle() != null && !base.player.movement.getVehicle().asset.hasZip && !base.player.movement.getVehicle().asset.hasBicycle) || Physics.Raycast(base.transform.position + Vector3.up, Quaternion.Euler(45f, LevelLighting.wind, 0f) * -Vector3.forward, 32f, RayMasks.BLOCK_WIND))
                {
                    ePlayerTemperature2 = EPlayerTemperature.COVERED;
                    lastCovered = simulation;
                    wasCovered = true;
                }
                else
                {
                    byte b2 = 1;
                    if (base.player.clothing.shirtAsset != null || base.player.clothing.vestAsset != null)
                    {
                        b2++;
                    }
                    if (base.player.clothing.pantsAsset != null)
                    {
                        b2++;
                    }
                    if (base.player.clothing.hatAsset != null)
                    {
                        b2++;
                    }
                    if (!wasCovered || simulation - lastCovered > 50 * b2)
                    {
                        ePlayerTemperature2 = EPlayerTemperature.FREEZING;
                        if (Provider.isServer && simulation - lastFreeze > 75)
                        {
                            lastFreeze = simulation;
                            byte b3 = 4;
                            if (base.player.clothing.shirtAsset != null || base.player.clothing.vestAsset != null)
                            {
                                b3--;
                            }
                            if (base.player.clothing.pantsAsset != null)
                            {
                                b3--;
                            }
                            if (base.player.clothing.hatAsset != null)
                            {
                                b3--;
                            }
                            askDamage(b3, Vector3.up, EDeathCause.FREEZING, ELimb.SPINE, Provider.server, out var _);
                        }
                    }
                    else
                    {
                        ePlayerTemperature2 = EPlayerTemperature.COLD;
                    }
                }
            }
            else
            {
                ePlayerTemperature2 = EPlayerTemperature.COLD;
                lastCovered = simulation;
                wasCovered = true;
            }
        }
        else
        {
            ePlayerTemperature2 = EPlayerTemperature.NONE;
        }
        if (ePlayerTemperature2 != temperature)
        {
            _temperature = ePlayerTemperature2;
            onTemperatureUpdated?.Invoke(temperature);
        }
```
It seems simulation is Seconds\*10(not verified)

- Covered → Has a roof, or is indoors/in a vehicle
- Freezing → In snow
- Burn & Acid → 
	- Does 10 dmg/sec

---
Sources:
[PlayerLife.cs](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/linux-client-preview/Assembly-CSharp/SDG.Unturned/PlayerLife.cs#L690) 