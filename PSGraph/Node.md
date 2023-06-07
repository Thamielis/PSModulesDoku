Node
----




### Synopsis




---


### Description

Used to specify a nodes attributes or placement within the flow.



---


### Examples
#### EXAMPLE 1
```PowerShell
graph g {
    node one,two,three
}
```

#### EXAMPLE 2
```PowerShell
graph g {
    node top @{shape='house'}
    node middle
    node bottom @{shape='invhouse'}
    edge top,middle,bottom
}
```

#### EXAMPLE 3
```PowerShell
graph g {
    node (1..10)
}
```



---


### Parameters
#### **Name**

The name of the node






|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[Object[]]`|true    |1       |true (ByValue)|



#### **NodeScript**

Script to run on each node






|Type           |Required|Position|PipelineInput|Aliases|
|---------------|--------|--------|-------------|-------|
|`[ScriptBlock]`|false   |named   |false        |Script |



#### **Attributes**

Node attributes to apply to this node






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |2       |false        |



#### **Ranked**

Will automatically add these nodes to a rank






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[Switch]`|false   |named   |false        |Rank   |



#### **Default**

not used anymore but offers backward compatibility or verbosity






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
I had conflits trying to alias Get-Node to node, so I droped the verb from the name.
If you have subgraphs, it works best to define the node inside the subgraph before giving it an edge



---


### Syntax
```PowerShell
Node [-Name] <Object[]> [-NodeScript <ScriptBlock>] [[-Attributes] <Hashtable>] [-Ranked] [-Default] [<CommonParameters>]
```
