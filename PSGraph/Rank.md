Rank
----




### Synopsis




---


### Description

Places specified nodes at the same level on the chart as a way to give some guidance to node layout



---


### Examples
#### EXAMPLE 1
```PowerShell
graph g {
    rank 1,3,5,7
    rank 2,4,6,8
    edge (1..8)
}
```

#### EXAMPLE 2
```PowerShell
$odd = @(1,3,5,7)
$even = @(2,4,6,8)
```
graph g {
    rank $odd
    rank $even
    edge $odd -to $even
}


---


### Parameters
#### **Nodes**

List of nodes to be on the same level as each other






|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[Object[]]`|true    |1       |true (ByValue)|



#### **AdditionalNodes**

Used to catch alternate style of specifying nodes






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[Object[]]`|false   |2       |false        |



#### **NodeScript**

Script to run on each node






|Type           |Required|Position|PipelineInput|Aliases|
|---------------|--------|--------|-------------|-------|
|`[ScriptBlock]`|false   |named   |false        |Script |





---


### Notes
Accepts an array of items or a list of strings.



---


### Syntax
```PowerShell
Rank [-Nodes] <Object[]> [[-AdditionalNodes] <Object[]>] [-NodeScript <ScriptBlock>] [<CommonParameters>]
```
