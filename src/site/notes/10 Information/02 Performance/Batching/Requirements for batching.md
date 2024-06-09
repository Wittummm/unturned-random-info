---
{"dg-publish":true,"permalink":"/10-information/02-performance/batching/requirements-for-batching/","created":"2024-03-31T21:20:28.137+07:00","updated":"2024-06-09T15:21:10.243+07:00"}
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


#### General batching details
 - Unity batches draw calls of GameObjects that use the same material. This means to get the best results from draw call batching, share materials among as many GameObjects as possible. If you have two material assets that are identical apart from their textures, you can combine the textures into a texture atlas. Unturned already does this [automatically](https://docs.smartlydressedgames.com/en/stable/mapping/level-batching.html#materials-eligible-for-atlas-inclusion) for the most part.

#### Mesh static batching
- Unturned does automatic runtime static batching see the detailed requirements for eligibility [here](https://docs.unity3d.com/Manual/static-batching.html).
- **Mesh** needs to be **cpu-readable**(this is only for mesh batching, not atlasing)
	- Not recommended to enable on models that will take up a lot of memory(lots of cumulative geometry data) as cpu-readable generally increases cpu memory usage.
	- If you want to still batch on lots of geometry, [GPU instancing](https://unturned-random-info.vercel.app/10-information/02-performance/gpu-instancing/) is a good alternative.
- Material needs to be the same.

#### Conclusion:
- GPU instancing for meshes that will have a lot of instances and geometry(like foliage). 
- Static batching for meshes does not have a lot of instances but static batching does not require the same meshes.

#### Sources
* [[10 Information/02 Performance/Batching/Z Source0\|Source File: Assembly-CSharp/SDG.Unturned/LevelBatching.cs]]
* [Official Unity Draw Call Batching Guide](https://docs.unity3d.com/Manual/DrawCallBatching.html)
* [Official Unity Static Batching Guide](https://docs.unity3d.com/Manual/static-batching.html) 
#requirements #batching