---
{"dg-publish":true,"permalink":"/10-information/02-performance/filtering-modes/","created":"2024-04-10T13:00:11.012+07:00","updated":"2024-04-10T13:12:25.650+07:00"}
---

Most textures in unturned are flat, muted, non-noisy textures so most do not need any special filtering. Most will be just fine with point filtering, unless there is a gradient in which you might use bi/trilinear
##### Notable differences:
* Point/Closest = pixelated look
* Bilinear = blurry, non-noisy at extreme angles and has some noticeable transition between mips
* Trilinear = blurry, non-noisy at extreme angles and reduced noticeable transitions between mips
* Anisotropic  = semi-sharp, non-noisy at extreme angles and smooth transitions
##### Guides
Flat, solid colors, uniform colors per face → Point filtering
Foliage(Rounded pixels) → Bilinear(or higher)
Gradient-like textures → Bilinear
Detailed textures → Trilinear(or higher)
Sharp, non-noisy, multiple colors per face(like a road) → Anisotropic

#texture-filtering #unpolished