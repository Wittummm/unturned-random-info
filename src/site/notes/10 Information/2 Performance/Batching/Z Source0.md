---
{"dg-publish":true,"permalink":"/10-information/2-performance/batching/z-source0/","created":"2024-03-31T22:31:54.842+07:00","updated":"2024-03-31T22:34:44.098+07:00"}
---

(This is so the main page isnt lengthy)

* [Source File: Assembly-CSharp/SDG.Unturned/LevelBatching.cs](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/linux-client-preview/Assembly-CSharp/SDG.Unturned/LevelBatching.cs) 
```csharp
// Required Shaders and Required resolution
if (texture2D.width > 128 || texture2D.height > 128)
            {
                if ((bool)shouldLogTextureAtlasExclusions && loggedTextures.Add(texture2D))
                {
                    UnturnedLog.info($"Excluding texture \"{texture2D.name}\" in material \"{material.name}\" renderer \"{renderer.GetSceneHierarchyPath()}\" from atlas because dimensions ({texture2D.width}x{texture2D.height}) are higher than limit ({128}x{128})");
                }
                return null;
            }
            if (texture2D.wrapMode != TextureWrapMode.Clamp)
            {
                if ((bool)shouldLogTextureAtlasExclusions && loggedTextures.Add(texture2D))
                {
                    UnturnedLog.info($"Excluding texture \"{texture2D.name}\" in material \"{material.name}\" renderer \"{renderer.GetSceneHierarchyPath()}\" from atlas because Wrap Mode ({texture2D.wrapMode}) is not Clamp");
                }
                return null;
            }
            if (shader.name == "Standard (Decalable)")
            {
                if (CanAtlasStandardMaterialSimpleOpaque(material, renderer, isSpecular: false) && CanAtlasTextureFilterMode(texture2D, material, renderer, FilterMode.Point))
                {
                    shaderGroup = standardDecalableOpaque;
                    texture.color = material.GetColor(propertyID_Color);
                }
            }
            else if (shader.name == "Standard (Specular setup) (Decalable)")
            {
                if (CanAtlasStandardMaterialSimpleOpaque(material, renderer, isSpecular: true) && CanAtlasTextureFilterMode(texture2D, material, renderer, FilterMode.Point))
                {
                    shaderGroup = standardSpecularSetupDecalableOpaque;
                    texture.color = material.GetColor(propertyID_Color);
                }
            }
            else if (shader.name == "Custom/Card")
            {
                shaderGroup = batchableCard;
            }
            else if (shader.name == "Custom/Foliage" && CanAtlasTextureFilterMode(texture2D, material, renderer, FilterMode.Trilinear))
            {
                shaderGroup = batchableFoliage;
            }
        }
``` 
```csharp
// Requires to be Cpu-Readable
private bool CanBatchMesh(Mesh mesh, Renderer renderer)
    {
        if (mesh.isReadable)
        {
            return true;
        }
        if ((bool)shouldLogTextureAtlasExclusions && loggedMeshes.Add(mesh))
        {
            UnturnedLog.info("Excluding mesh \"" + mesh.name + "\" in renderer \"" + renderer.GetSceneHierarchyPath() + "\" from level batching because it is not CPU-readable");
        }
        return false;
    }
```