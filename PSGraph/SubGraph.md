SubGraph
--------




### Synopsis




---


### Description

A graph that is nested inside another graph to sub group elements



---


### Examples
#### EXAMPLE 1
```PowerShell
graph g {
    node top,bottom @{shape='rect'}
    subgraph 0 {
        node left,right
    }
    edge top -to left,right
    edge left,right -to bottom
}
```



---


### Parameters
#### **Name**

Name of subgraph






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[Object]`|true    |1       |false        |ID     |



#### **ScriptBlock**

The commands to execute inside the subgraph






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ScriptBlock]`|true    |1       |false        |



#### **Attributes**

Hashtable that gets translated to graph attributes






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|true    |2       |false        |





---


### Notes
This is just like the graph or digraph, except the name must match cluster_#
The numbering must start at 0 and work up or the processor will fail.



---


### Syntax
```PowerShell
SubGraph [-ScriptBlock] <ScriptBlock> [<CommonParameters>]
```
```PowerShell
SubGraph [-Name] <Object> [-ScriptBlock] <ScriptBlock> [-Attributes] <Hashtable> [<CommonParameters>]
```
```PowerShell
SubGraph [-Name] <Object> [-ScriptBlock] <ScriptBlock> [<CommonParameters>]
```
```PowerShell
SubGraph [-ScriptBlock] <ScriptBlock> [-Attributes] <Hashtable> [<CommonParameters>]
```
