---
{"dg-publish":true,"permalink":"/05-guides/6-modules/self-ref/your-project-name-module/","created":"2024-07-15T13:25:34.567+07:00","updated":"2024-07-15T13:29:28.222+07:00"}
---

`json` file format
```json
{ 
	"IsEnabled": true, 
	"Name": "Project Name", 
	"Version": "1.0.0.0", 
	"Assemblies": 
	[ 
		{ 
			"Path": "projectdllname.dll", 
			"Role": "Both_Optional" // Server, Client, Both_Optional, Both_Required
		} 
	] 
}
```