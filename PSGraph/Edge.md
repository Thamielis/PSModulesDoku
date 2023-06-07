Edge
----




### Synopsis




---


### Description

This defines an edge between two or more nodes



---


### Examples
#### EXAMPLE 1
```PowerShell
Graph g {
    Edge FirstNode SecondNode
}
```
Generates this graph syntax:

digraph g {
    "FirstNode"->"SecondNode"
}
#### EXAMPLE 2
```PowerShell
$folder = Get-ChildItem -Recurse -Directory
graph g {
    $folder | %{ edge $_.parent $_.name }
}
```
# with parameter names specified
graph g {
    $folder | %{ edge -From $_.parent -To $_.name }
}

# with scripted properties
graph g {
    edge $folder -FromScript {$_.parent} -ToScript {$_.name}
}
#### EXAMPLE 3
```PowerShell
$folder = Get-ChildItem -Recurse -Directory
```

#### EXAMPLE 4
```PowerShell
graph g {
    edge (1..3) (5..7)
    edge top bottom @{label="line label"}
    edge (10..13)
    edge one,two,three,four
}
```



---


### Parameters
#### **From**

start node or source of edge






|Type        |Required|Position|PipelineInput|Aliases                                                  |
|------------|--------|--------|-------------|---------------------------------------------------------|
|`[String[]]`|true    |1       |false        |NodeName<br/>Name<br/>SourceName<br/>LeftHandSide<br/>lhs|



#### **To**

Destination node or target of edge






|Type        |Required|Position|PipelineInput|Aliases                                             |
|------------|--------|--------|-------------|----------------------------------------------------|
|`[String[]]`|false   |2       |false        |Destination<br/>TargetName<br/>RightHandSide<br/>rhs|



#### **Attributes**

Hashtable that gets translated to an edge modifier






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |3       |false        |



#### **Node**

a list of nodes to process






|Type        |Required|Position|PipelineInput |Aliases    |
|------------|--------|--------|--------------|-----------|
|`[Object[]]`|true    |1       |true (ByValue)|InputObject|



#### **FromScript**

start node script or source of edge






|Type           |Required|Position|PipelineInput|Aliases                         |
|---------------|--------|--------|-------------|--------------------------------|
|`[ScriptBlock]`|false   |named   |false        |FromScriptBlock<br/>SourceScript|



#### **ToScript**

Destination node script or target of edge






|Type           |Required|Position|PipelineInput|Aliases                       |
|---------------|--------|--------|-------------|------------------------------|
|`[ScriptBlock]`|false   |named   |false        |ToScriptBlock<br/>TargetScript|



#### **LiteralAttribute**

A string for using native attribute syntax






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Default**

Not used, but can be specified for verbosity






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
If an array is specified for the From property, but not for the To property, then the From list will be procesed in order and will map the array in a chain.



---


### Syntax
```PowerShell
Edge [-From] <String[]> [[-To] <String[]>] [[-Attributes] <Hashtable>] [-LiteralAttribute <String>] [-Default] [<CommonParameters>]
```
```PowerShell
Edge [-From] <String[]> [-Attributes] <Hashtable> [-LiteralAttribute <String>] [-Default] [<CommonParameters>]
```
```PowerShell
Edge [[-Attributes] <Hashtable>] [-Node] <Object[]> [-FromScript <ScriptBlock>] [-ToScript <ScriptBlock>] [-LiteralAttribute <String>] [-Default] [<CommonParameters>]
```
