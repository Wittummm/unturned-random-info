---
{"dg-publish":true,"permalink":"/05-guides/6-modules/wip-setting-up-net-for-visual-studio-code-unturned/","created":"2024-07-02T20:01:52.928+07:00","updated":"2024-07-23T08:59:00.096+07:00"}
---

##### Warning(also Note to self)
I can barely get modules working using VSC currently. So i will probably also make a subsequent one on Visual Studio. VSC is very buggy and really stubborn and doesn't want to work so this guide should not even be used atm. Until i figure out how to set it up perfectly this guide should be disregarded.

#### Preface
This assumes you know the basics of VS Code. The guide will still probably somewhat help even if you don't know but it is recommended to learn VSC first. Anyways, this guide is targeted towards setting VSC for Unturned.

1. [Setting up for .NET](https://code.visualstudio.com/docs/csharp/get-started) 
	1. Download [Visual Studio Code](https://code.visualstudio.com/) obviously..
	2. Download .NET Standard 2.1 or the lastest .NET Framework version(must be 4.6.1 or above)
	3. Download Visual Studio Code extensions
		- [NuGet Package Manager](https://marketplace.visualstudio.com/items?itemName=jmrog.vscode-nuget-package-manager) extension
		- [C# Devkit](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit) extension
		- [ilspy-vscode](https://marketplace.visualstudio.com/items?itemName=icsharpcode.ilspy-vscode) extension
	1. Open the Command Palette using `⇧⌘P`, run `.NET: New Project` and use the *Console App* template.
2. Setting up the Workspace for Unturned
	1. Download NuGet packages
		- Client Side modules
			- RocketModFix.UnityEngine.Redist
			- RocketModFix.Unturned.Redist
		- Plugins(**Verify if below works like just using template is enough? or needs to install more packages**)
			Use either a [OpenMod](https://github.com/openmod/openmod/tree/main/templates) or [RocketMod](https://github.com/RestoreMonarchyPlugins/UnturnedTemplates) template or manually download packages below(Only for RocketMod). You can copy the files directly or use a templater in your IDE.
			- RestoreMonarchy.RocketRedist or (Rocket.API, Rocket.Core, Rocket.Unturned, etc?)
			- RestoreMonarchy.UnturnedRedist or (etc?)
	1. Set up Module files in your project folder (Only required when making modules)
		- Create a `English.dat` (example [here](https://unturned-random-info.vercel.app/05-guides/6-modules/self-ref/english-dat/))
		- Create a `YourProjectName.module` (example [here](https://unturned-random-info.vercel.app/05-guides/6-modules/self-ref/your-project-name-module/))
		- Create a `Nexus.cs` file for initialization and shutdown (example [here](https://unturned-random-info.vercel.app/05-guides/6-modules/self-ref/nexus-cs/)) **(WIP, verify code)**
--- 
Sources (sources in the guide itself is not listed):
[NET version msg](https://discord.com/channels/324229387295653889/1210098272044064799/1210280064038604881) 
[(Unofficial) Unturned Docs 2018: Creating a module](https://unturneddocs.github.io/UnturnedDocs/#/guides/creating_a_module) 
[JDance's Creating Modules Guide](https://forum.smartlydressedgames.com/t/guide-creating-modules/23749) It is now deleted so it is all from my recollection(If he posts a new one or I find a similar one I might update it)
#client-modules #set-up