Export-PSGraph
--------------




### Synopsis




---


### Description

Invokes the graphviz binaries to generate a graph.



---


### Examples
#### EXAMPLE 1
```PowerShell
Export-PSGraph -Source graph.dot -OutputFormat png
```

#### EXAMPLE 2
```PowerShell
graph g {
    edge (3..6)
    edge (5..2)
} | Export-PSGraph -Destination $env:temp\test.png
```



---


### Parameters
#### **Source**

The GraphViz file to process or contents of the graph in Dot notation






|Type        |Required|Position|PipelineInput |Aliases                             |
|------------|--------|--------|--------------|------------------------------------|
|`[String[]]`|false   |named   |true (ByValue)|InputObject<br/>Graph<br/>SourcePath|



#### **DestinationPath**

The destination for the generated file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |1       |false        |



#### **OutputFormat**

The file type used when generating an image



Valid Values:

* jpg
* png
* gif
* imap
* cmapx
* jp2
* json
* pdf
* plain
* dot
* svg






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **LayoutEngine**

The layout engine used to generate the image



Valid Values:

* Hierarchical
* SpringModelSmall
* SpringModelMedium
* SpringModelLarge
* Radial
* Circular
* dot
* neato
* fdp
* sfdp
* twopi
* circo






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **GraphVizPath**

Path or paths to the dot graphviz executable. Some sensible defaults are used if nothing is passed.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |false        |



#### **ShowGraph**

Launches the graph when done






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
The source can either be files or piped graph data.

It checks the piped data for file paths. If it cannot find a file, it assumes it is graph data.
This may give unexpected errors when the file does not exist.



---


### Syntax
```PowerShell
Export-PSGraph [-Source <String[]>] [[-DestinationPath] <String>] [-OutputFormat <String>] [-LayoutEngine <String>] [-GraphVizPath <String[]>] [-ShowGraph] [<CommonParameters>]
```
