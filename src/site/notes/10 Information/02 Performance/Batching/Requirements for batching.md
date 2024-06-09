---
{"dg-publish":true,"permalink":"/10-information/02-performance/batching/requirements-for-batching/","created":"2024-03-31T21:20:28.137+07:00","updated":"2024-06-09T15:00:45.754+07:00"}
---


#### Texture Atlasing
- ##### Material
	- The **shaders**: `Standard (Decalable)`, `Standard (Specular setup) (Decalable)`, `Custom/Card`, `Custom/Foliage`
	- **Filtering mode** must be: 
		- `Point` if `Standard (Decalable)` or`Standard (Specular setup) (Decalable)`
		- `Trilinear` if `Custom/Foliage`
		- *Any* if `Custom/Card`
	- **Cannot use** (most?) **PBR**: specular, metallic, smoothness, glossiness, normal map, emission, parallax mapping.
	- **Height or width** cannot be more than **128** pixels.
	- **Wrap mode** must be `Clamp`
	- **Mode** has to be `Opaque`
- ##### Mesh
	- **UVs** must **not be out-of-bounds**.


#### Mesh batching
**Mesh** needs to be **cpu-readable**(this is only for mesh batching, not atlasing)
	- Not recommended to enable on models that will take up a lot of memory(lots of cumulative geometry data) as cpu-readable generally increases cpu memory usage.
	- If you want to still batch on lots of geometry, [GPU instancing](https://unturned-random-info.vercel.app/10-information/02-performance/gpu-instancing/) is a good alternative.

#### Sources
* [[10 Information/02 Performance/Batching/Z Source0\|Source File: Assembly-CSharp/SDG.Unturned/LevelBatching.cs]]
#requirements #batching