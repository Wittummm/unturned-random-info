---
{"dg-publish":true,"permalink":"/05-guides/2-performance/alpha-clipping-vs-alpha-blending/","created":"2024-03-31T23:05:38.184+07:00","updated":"2024-04-01T22:24:44.886+07:00"}
---

### Alpha Clipping/Testing
Pro: Writes to depth buffer, meaning things behind it does not need to be rendered
Con: Writes to depth buffer, potentially using some performance
### Alpha Blending
Pro: Does not write to depth buffer
Con: Does not write to depth buffer, needing to draw everything behind it
### Conclusion
Alpha blending should be avoided when there's a lot of overdraw. Alpha clipping can be used in most cases and generally has better performance, as it eliminates overdraw.

Note: I'm unsure why "noisy or thin" textures decrease performance when using alpha clipping.
#### Sources
[Unity Forums post by bgolus and burningmime: Is Alpha Clipping better for performance?](https://forum.unity.com/threads/is-alpha-clipping-better-for-performance.1359176/#:~:text=This%20can%20be%20a%20significant,performance%20benefits%20over%20alpha%20blending.)
#### Unused sources
[Unity Forums post by bgolus: Alpha To Coverage Performance](https://forum.unity.com/threads/alpha-to-coverage-performance.1200853/)
##### Possibly related details
* [Samsung: Tile based rendering](https://developer.samsung.com/galaxy-gamedev/resources/articles/gpu-framebuffer.html)
* [Wikipedia: Tile based rendering](https://en.m.wikipedia.org/wiki/Tiled_rendering#)
* Tile sizes are
	* Mobile(ARM) - 16x16 to 32x32
	* Desktop - 32x32 to 64x64(occasionally 128x128+) or dynamic tile size 

##### Connections
My Medium post references this note

**TODO: Write this as a post to my Medium and add it here this page will then redirect to that link when done**