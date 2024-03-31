---
{"dg-publish":true,"permalink":"/10-information/2-performance/batching/requirements-for-batching/","created":"2024-03-31T21:20:28.137+07:00","updated":"2024-03-31T22:38:28.325+07:00"}
---

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
	- **Mesh** needs to be **cpu-readable**(might not be good to enable on a high memory model as cpu-readable generally increases ram usage)

#### Sources
* [[10 Information/2 Performance/Batching/Z Source0\|Source File: Assembly-CSharp/SDG.Unturned/LevelBatching.cs]]
