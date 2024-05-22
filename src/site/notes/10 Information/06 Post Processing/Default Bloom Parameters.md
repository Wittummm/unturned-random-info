---
{"dg-publish":true,"permalink":"/10-information/06-post-processing/default-bloom-parameters/","created":"2024-05-22T15:00:56.867+07:00","updated":"2024-05-22T15:17:13.302+07:00"}
---

```csharp
bloom.intensity.Override(1f);
bloom.softKnee.Override(0f);
```
* Threshold: 1(Default)
* Intensity: 1
* SoftKnee: 0
* Clamp: 65472(Default)
* Diffusion: 7(Default)
* Anamorphic Ratio: 0(Default)
* Color: Default
* Fast mode: False(Default)
(Infered, not verified in-game values)

Extra:
- Fast Mode: This toggle option lowers the quality of the Bloom to boost performance. It’s generally recommended for mobile and low-end platforms, but can still give a nice performance boost even on high-end PCs and consoles.

---
Sources: 
[UnturnedPostProcess.cs, Line 37](<UnturnedPostProcess.cs, Line 37>) 
#bloom 