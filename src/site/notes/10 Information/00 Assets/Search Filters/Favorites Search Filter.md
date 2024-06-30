---
{"dg-publish":true,"permalink":"/10-information/00-assets/search-filters/favorites-search-filter/","created":"2024-06-30T19:43:28.348+07:00","updated":"2024-06-30T20:18:00.673+07:00"}
---

```csharp
GameDataDirectory = new DirectoryInfo(Application.dataPath);
GameDirectory = GameDataDirectory.Parent;
```

> Entering “fv:xyz” in the search bar loads xyz.txt from the game folder, and will match any of the lines in the file. Empty lines and lines starting with “//” (comments) are ignored. The .txt file extension was chosen because it is the notepad default.
> 
> Recursive usage of filters is supported, so multiple favorite searches can be nested, or other filter types e.g. “Tunnel mb:core” includes tunnels from the vanilla objects.

Root folder:
- MacOS: Unturned.app
- Windows/Linux: Folder that has the executable and Unturned_Data

Related:
[Masterbundle Search Filter](https://unturned-random-info.vercel.app/10-information/00-assets/search-filters/masterbundle-search-filter/) 

---
Sources:
[Application.dataPath](https://docs.unity3d.com/ScriptReference/Application-dataPath.html) 
[UnityPaths.cs](https://github.com/Unturned-Datamining/Unturned-Datamining/blob/8d16423d590bc3a32d50bb31dce671d2b4852547/UnityEx/Unturned.UnityEx/UnityPaths.cs#L23) 
[UnturnedPaths.cs](https://github.com/Unturned-Datamining/Unturned-Datamining/blob/8d16423d590bc3a32d50bb31dce671d2b4852547/Assembly-CSharp/SDG.Unturned/UnturnedPaths.cs) 
#search-filter 