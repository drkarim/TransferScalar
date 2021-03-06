# TransferScalar

A VTK utility program that will copy point data scalars between two VTK surface meshes. It only works on Polygonal data. 

For copying the scalar data, it currently only has two options: 

- Vertex index copy ```--index``` using vertex point IDs. Ensure source and target have equal vertices
- Nearest neighbour ```--nn``` copies from the nearest vertex on source. Source and target dont need to have equal number of vertices

Note that data is copied from source to target. Also, note that the ICP option ```--icp``` does not work and it has bugs 

## Usage 

```
Required parameters: 
	-source source 
	-target target 
	-o output
	--nn (use nearest neighbour)
	--index (use vertex index to copy) 
	--icp (does not work)

```

## Considerations 

I have tried to list some important points to consider before using this technique: 

* Data is copied from source to target
* The ```--nn``` does not require same number of vertices between source and target
* The ```--index``` copies based on vertex indices or point IDs. Ensure that both target and source have same number of vertices
* ICP option does not work yet
* Use NN when both surfaces dont have equal number of points. 
* Note this method assumes that the surfaces are aligned approximately and data can be copied over reliably from one to the other
* In nearest neighbour search, if a nearest neighbour is not found due to any reason, a scalar value of 0 is copied over


## Author 

```
Dr. Rashed Karim 
Department of Biomedical Engineering 
King's College London 
```
