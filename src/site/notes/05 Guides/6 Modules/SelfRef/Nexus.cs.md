---
{"dg-publish":true,"permalink":"/05-guides/6-modules/self-ref/nexus-cs/","created":"2024-07-15T13:27:13.908+07:00","updated":"2024-07-15T13:29:06.282+07:00"}
---

```csharp
using System; 
using SDG.Framework.Modules; 

namespace ExampleModule 
{ 
	public class ExampleModuleNexus : IModuleNexus 
	{ 
		public void initialize() { 
			Console.WriteLine("Example module successfully loaded!"); 
		} 
		public void shutdown() { 
			Console.WriteLine("Example module got showdown :( "); 
		} 
	} 
}
```