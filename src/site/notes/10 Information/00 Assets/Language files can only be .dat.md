---
{"dg-publish":true,"permalink":"/10-information/00-assets/language-files-can-only-be-dat/","created":"2024-05-30T20:15:11.899+07:00","updated":"2024-05-30T20:17:43.658+07:00"}
---

```csharp
if (checkForTranslations) {
	string path = Path.Combine(directoryName, owner.language + ".dat");
	string path2 = Path.Combine(directoryName, "English.dat");
	if (File.Exists(path))
	{
		translationData = ReadFileWithoutHash(path);
		if (!owner.languageIsEnglish && File.Exists(path2))
		{
			fallbackTranslationData = ReadFileWithoutHash(path2);
		}
	}
	else if (File.Exists(path2))
	{
		translationData = ReadFileWithoutHash(path2);
	}
}
```

Sources:
[AssetWorker.cs](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/linux-client-preview/Assembly-CSharp/SDG.Unturned/AssetsWorker.cs) 

#language 