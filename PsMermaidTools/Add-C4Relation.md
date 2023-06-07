Add-MermaidC4Relation
---------------------




### Synopsis
Add a relation to a diagram.



---


### Description

Create a relation between two components and add it to an C4 diagram.



---


### Related Links
* [https://abbgrade.github.io/PsMermaidTools/docs/Add-MermaidC4Relation.html](https://abbgrade.github.io/PsMermaidTools/docs/Add-MermaidC4Relation.html)



* [https://mermaid.js.org/syntax/c4c.html#c4-component-diagram-c4component](https://mermaid.js.org/syntax/c4c.html#c4-component-diagram-c4component)





---


### Parameters
#### **Diagram**

The diagram, that the relation is added to.






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[Object]`|true    |named   |true (ByValue)|



#### **From**

The first entity of the relation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **To**

The second entity of the relation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |2       |false        |



#### **Label**

Describes the relationship.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |3       |false        |



#### **Technology**

The relation technology / implementation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Description**

Describes the relation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |





---


### Inputs
C4 diagram object.



---


### Outputs
* None.






---


### Syntax
```PowerShell
Add-MermaidC4Relation -Diagram <Object> [-From] <String> [-To] <String> [-Label] <String> [-Technology <String>] [-Description <String>] [<CommonParameters>]
```
