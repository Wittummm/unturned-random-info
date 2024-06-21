---
{"dg-publish":true,"permalink":"/10-information/02-performance/analyzing-level-visibility/","created":"2024-06-21T19:20:58.882+07:00","updated":"2024-06-21T20:35:17.734+07:00"}
---

```csharp
// This code may be modified for easier readability.
private static void update(int x, int y)
    {
        for (int i = 0; i < DEBUG_SIZE; i++)
        {
            for (int j = 0; j < DEBUG_SIZE; j++)
            {
                int num = (i * DEBUG_SIZE) + j;
                int num2 = (x - (DEBUG_SIZE / 2)) + i; // normalized X coord
                int num3 = (y - (DEBUG_SIZE / 2)) + j; // normalized Y coord
                ISleekLabel sleekLabel = regionLabels[num];
                if (!Regions.checkSafe(num2, num3)) // probably checks if its in bounds(not verified)
                {
                    continue; // if not in bounds; skip
                }
                int num4 = LevelObjects.objects[num2, num3].Count + LevelGround.trees[num2, num3].Count; // count of objects and trees(and maybe resources) at (X, Y)
                int num5 = LevelObjects.total + LevelGround.total;  // count of all objects and trees(maybe resource) on the whole map
                double num6 = Math.Round(((double)num4 / (double)num5) * 1000.0) / 10.0; // round(percentage of whole map * 1000) / 10 -> Percentage of objects and trees(maybe resources) in the chunk, rounded to the first decimal -> AB.C
                int num7 = 0; // total triangles of Objects and Trees(maybe resources) at (X, Y)
                for (int k = 0; k < LevelObjects.objects[num2, num3].Count; k++)
                {
                    LevelObject levelObject = LevelObjects.objects[num2, num3][k];
                    if (!levelObject.transform)
                    {
                        continue;
                    }
                    levelObject.transform.GetComponents(meshes); // outputs the variable: "mesh"
                    if (meshes.Count == 0)
                    {
                        Transform transform = levelObject.transform.Find("Model_0");
                        if ((bool)transform) // if has Model_0
                        {
                            transform.GetComponentsInChildren(includeInactive: true, meshes);
                        }
                    }
                    if (meshes.Count == 0) // if nothing in Model_0, skip
                    {
                        continue;
                    }
                    for (int l = 0; l < meshes.Count; l++)
                    {
                        Mesh sharedMesh = meshes[l].sharedMesh;
                        if ((bool)sharedMesh)
                        {
                            num7 += sharedMesh.triangles.Length; 
                            // adds amount of triangles in the mesh
                        }
                    }
                }
                
	            // same as Objects, ill just skip this
                for (int m = 0; m < LevelGround.trees[num2, num3].Count; m++)
                {
                    ResourceSpawnpoint resourceSpawnpoint = LevelGround.trees[num2, num3][m];
                    if (!resourceSpawnpoint.model)
                    {
                        continue;
                    }
                    resourceSpawnpoint.model.GetComponents(meshes);
                    if (meshes.Count == 0)
                    {
                        Transform transform2 = resourceSpawnpoint.model.Find("Model_0");
                        if ((bool)transform2)
                        {
                            transform2.GetComponentsInChildren(includeInactive: true, meshes);
                        }
                    }
                    if (meshes.Count == 0)
                    {
                        continue;
                    }
                    for (int n = 0; n < meshes.Count; n++)
                    {
                        Mesh sharedMesh2 = meshes[n].sharedMesh;
                        if ((bool)sharedMesh2)
                        {
                            num7 += sharedMesh2.triangles.Length;
                        }
                    }
                }
                long num8 = (long)num4 * (long)num7; // ObjectCount + TotalTriangles -> PerfFactor
                float quality = Mathf.Clamp01((float)(1.0 - ((double)num8 / 50_000_000.0))); // (1 - (PerfFactor/50Mil)) -> lower is worsep
                sleekLabel.Text = localization.format("Point", num2, num3);
                sleekLabel.Text = sleekLabel.Text + "\n" + localization.format("Objects", num4, num6); // Count and Percentage
                sleekLabel.Text = sleekLabel.Text + "\n" + localization.format("Triangles", num7); // Total triangles
                if (num4 == 0 && num7 == 0)
                {
                    sleekLabel.TextColor = Color.white;
                }
                else
                {
                    sleekLabel.TextColor = ItemTool.getQualityColor(quality);
                    // Red to Green -> 0 to 1
                }
            }
        }
    }
```
 The visibility seems to do a general performance analysis and it should not be the final say in performance. Analysis by a person who understands the technicals of game performance will be better. The best performance indicator is to test and profile the map in practice, theory always loses.
---
Sources:
[EditorLevelVisibilityUI.cs; Line 134](https://raw.githubusercontent.com/Unturned-Datamining/Unturned-Datamining/linux-client-preview/Assembly-CSharp/SDG.Unturned/EditorLevelVisibilityUI.cs#L139)