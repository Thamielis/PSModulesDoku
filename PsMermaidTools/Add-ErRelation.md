Add-MermaidErRelation
---------------------




### Synopsis
Add a relation to a erDiagram.



---


### Description

Add a relation to a er diagram. Used entities do not to be defined before.



---


### Related Links
* [https://mermaid-js.github.io/mermaid/#/entityRelationshipDiagram?id=entities-and-relationships](https://mermaid-js.github.io/mermaid/#/entityRelationshipDiagram?id=entities-and-relationships)





---


### Examples
#### EXAMPLE 1
```PowerShell
$diagram = New-MermaidDiagram -ErDiagram
PS C:\> $diagram | Add-MermaidErRelation Exactly-one Customer places Zero-or-more Order
PS C:\> $diagram | Add-MermaidErRelation Exactly-one Order contains One-or-more LineItem
PS C:\> $diagram | Add-MermaidErRelation One-or-more Customer uses One-or-more DeliveryAddress -NonIdentifying
PS C:\> $diagram | ConvertTo-MermaidString
erDiagram
    Customer ||--o{ Order : places
    Order ||--|{ LineItem : contains
    Customer }|..|{ DeliveryAddress : uses
```
Create a erDiagram, add a few relations and convert it to a diagram string.


---


### Parameters
#### **Diagram**

The diagram, that the relation is added to.






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[Object]`|false   |named   |true (ByValue)|



#### **Entity**

The first entity of the relation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **FirstEntity**

The first entity of the relation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |2       |false        |



#### **FirstCardinality**

How often the first entity exists in the relation.



Valid Values:

* Zero-or-one
* Exactly-one
* Zero-or-more
* One-or-more






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **SecondEntity**

The second entity of the relation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |5       |false        |



#### **SecondCardinality**

How often the second entity exists in the relation.



Valid Values:

* Zero-or-one
* Exactly-one
* Zero-or-more
* One-or-more






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |4       |false        |



#### **Label**

Describes the relationship.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |3       |false        |



#### **NonIdentifying**

Specifies if one of the entities may exist without the other.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Inputs
Mermaid diagram definition object.



---


### Outputs
* None.






---


### Syntax
```PowerShell
Add-MermaidErRelation [-Diagram <Object>] -Entity <String> [<CommonParameters>]
```
```PowerShell
Add-MermaidErRelation [-Diagram <Object>] [-FirstEntity] <String> [-FirstCardinality] <String> [-SecondEntity] <String> [-SecondCardinality] <String> [-Label] <String> [-NonIdentifying] [<CommonParameters>]
```
