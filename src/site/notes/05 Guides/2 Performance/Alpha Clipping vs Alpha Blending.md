---
{"dg-publish":true,"permalink":"/05-guides/2-performance/alpha-clipping-vs-alpha-blending/","created":"2024-03-31T23:05:38.184+07:00","updated":"2024-04-01T00:00:16.924+07:00"}
---

### Alpha Clipping/Testing
Pro: Writes to depth buffer, meaning things behind it does not need to be rendered
Con: Writes to depth buffer, potentially using some performance

As (ARM) GPUs render in tiles of 16x16 to 64x64 there can be slight overdraw. When theres even a single pixel in a tile it would need to mark the whole tile as opaque. I do not know much about the inner workings of GPUs so **this is very speculative**.
### Alpha Blending
Pro: Does not write to depth buffer
Con: Does not write to depth buffer, needing to draw everything behind it
### Conclusion
Alpha blending should be avoided when there's a lot of overdraw. Alpha clipping can be used in most cases and generally has better performance,
Alpha clipping reduces overdraw at the cost of needing to write to the depth buffer.
#### Sources
[Unity Forums: Is Alpha Clipping better for performance?](https://forum.unity.com/threads/is-alpha-clipping-better-for-performance.1359176/#:~:text=This%20can%20be%20a%20significant,performance%20benefits%20over%20alpha%20blending.) 
##### Unrelated details
* [Samsung: Tile based rendering](https://developer.samsung.com/galaxy-gamedev/resources/articles/gpu-framebuffer.html)
* [Wikipedia: Tile based rendering](https://en.m.wikipedia.org/wiki/Tiled_rendering#)
* Tile sizes are
	* Mobile(ARM) - 16x16 to 32x32
	* Desktop - 32x32 to 64x64(occasionally 128x128+) or dynamic tile size 

**TODO: Write this as a post to my Medium and add it here this page will then redirect to that link when done**