---
{"dg-publish":true,"permalink":"/10-information/02-performance/manual-culling-volumes/","created":"2024-06-02T23:22:48.285+07:00","updated":"2024-06-02T23:27:13.086+07:00"}
---

- LOD: None, Area, Mesh; 
	- None doesn't add any culling volumes.
	- Mesh gets the bounding box of the whole mesh. 
	- Area gets the bounding box of the Occlusion Area(s) component in GameObjects Name "Occlusion"
- LOD_Bias: float; `64 * LOD_Bias` in meters, the distance to start culling the object from.

Extra: 
[Manual Culling Volume Bias](https://unturned-random-info.vercel.app/10-information/08-limits/manual-culling-volume-bias/) 

Sources:
(To be Added)