Graph
-----




### Synopsis




---


### Description

Defines a graph. The base collection that holds all other graph elements



---


### Examples
#### EXAMPLE 1
```PowerShell
graph g {
    node top,left,right @{shape='rectangle'}
    rank left,right
    edge top left,right
}
```

#### EXAMPLE 2
```PowerShell
$dot = graph {
    edge hello world
}
```



---


### Parameters
#### **Name**

Name or ID of the graph






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **ScriptBlock**

The commands to execute inside the graph






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ScriptBlock]`|true    |1       |false        |



#### **Attributes**

Hashtable that gets translated to graph attributes






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|true    |2       |false        |



#### **Type**

Keyword that initiates the graph






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |





---


### Outputs
* [String](https://learn.microsoft.com/en-us/dotnet/api/System.String)






---


### Notes
The output is a string so it can be saved to a variable or piped to other commands



---


### Syntax
```PowerShell
Graph [-ScriptBlock] <ScriptBlock> [-Type <String>] [<CommonParameters>]
```
```PowerShell
Graph [-Name] <String> [-ScriptBlock] <ScriptBlock> [-Attributes] <Hashtable> [-Type <String>] [<CommonParameters>]
```
```PowerShell
Graph [-Name] <String> [-ScriptBlock] <ScriptBlock> [-Type <String>] [<CommonParameters>]
```
```PowerShell
Graph [-ScriptBlock] <ScriptBlock> [-Attributes] <Hashtable> [-Type <String>] [<CommonParameters>]
```
