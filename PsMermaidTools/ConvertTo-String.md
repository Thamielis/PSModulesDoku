ConvertTo-MermaidString
-----------------------




### Synopsis
Converts a mermaid definition to string.



---


### Description

Generates mermaid syntax for definitions created with this module.



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
#### **Type**

The diagram link type.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **Relations**

Collection of relations.






|Type          |Required|Position|PipelineInput        |
|--------------|--------|--------|---------------------|
|`[PSObject[]]`|true    |named   |true (ByPropertyName)|



#### **Orientation**

Orientation of the flowchart.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **Nodes**

Collection of nodes for a flowchart.






|Type          |Required|Position|PipelineInput        |
|--------------|--------|--------|---------------------|
|`[PSObject[]]`|true    |named   |true (ByPropertyName)|



#### **Links**

Collection of links for a flowchart.






|Type          |Required|Position|PipelineInput        |
|--------------|--------|--------|---------------------|
|`[PSObject[]]`|true    |named   |true (ByPropertyName)|



#### **ContainerBoundaries**

Collection of container boundaries for a C4Component diagram.






|Type          |Required|Position|PipelineInput        |
|--------------|--------|--------|---------------------|
|`[PSObject[]]`|true    |named   |true (ByPropertyName)|



#### **Components**

Collection of components for a C4Component diagram.






|Type          |Required|Position|PipelineInput        |
|--------------|--------|--------|---------------------|
|`[PSObject[]]`|true    |named   |true (ByPropertyName)|



#### **From**




|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|false   |named   |true (ByPropertyName)|



#### **To**




|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|false   |named   |true (ByPropertyName)|



#### **Technology**

The component technology / implementation.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|false   |named   |true (ByPropertyName)|



#### **Description**

Describes the component.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|false   |named   |true (ByPropertyName)|



#### **FirstEntity**

First entity of the relation.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **Relationship**

Relationship of the relation.






|Type        |Required|Position|PipelineInput        |
|------------|--------|--------|---------------------|
|`[PSObject]`|false   |named   |true (ByPropertyName)|



#### **SecondEntity**

First second of the relation.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|false   |named   |true (ByPropertyName)|



#### **Label**

Describes the relation.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|false   |named   |true (ByPropertyName)|



#### **SourceNode**

Source node of the link.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **SourceHead**

Source node of the link.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **DestinationNode**

Destination node of the link.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **DestinationHead**

Destination node of the link.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **Text**

Link text.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|false   |named   |true (ByPropertyName)|



#### **Line**




|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **Key**

Indentifier of the node/container/component.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **Name**

Name of the node/container.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **Shape**

Shape of the node.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **FirstCardinality**

Cardinality of the first entity.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **SecondCardinality**

Cardinality of the second entity.






|Type      |Required|Position|PipelineInput        |
|----------|--------|--------|---------------------|
|`[String]`|true    |named   |true (ByPropertyName)|



#### **Identifying**

Flags if one entity may exist without the other.
endregion






|Type       |Required|Position|PipelineInput        |
|-----------|--------|--------|---------------------|
|`[Boolean]`|true    |named   |true (ByPropertyName)|





---


### Inputs
Mermaid diagram definition object.



---


### Outputs
* String.






---


### Syntax
```PowerShell
ConvertTo-MermaidString -Type <String> -Relations <PSObject[]> -ContainerBoundaries <PSObject[]> [<CommonParameters>]
```
```PowerShell
ConvertTo-MermaidString -Type <String> -Orientation <String> -Nodes <PSObject[]> -Links <PSObject[]> [<CommonParameters>]
```
```PowerShell
ConvertTo-MermaidString -Type <String> -Relations <PSObject[]> [<CommonParameters>]
```
```PowerShell
ConvertTo-MermaidString -Components <PSObject[]> -Key <String> -Name <String> [<CommonParameters>]
```
```PowerShell
ConvertTo-MermaidString [-From <String>] [-To <String>] [-Technology <String>] [-Description <String>] [-Label <String>] [<CommonParameters>]
```
```PowerShell
ConvertTo-MermaidString [-Technology <String>] [-Description <String>] -Key <String> -Name <String> [<CommonParameters>]
```
```PowerShell
ConvertTo-MermaidString -FirstEntity <String> [-Relationship <PSObject>] [-SecondEntity <String>] [-Label <String>] [<CommonParameters>]
```
```PowerShell
ConvertTo-MermaidString -SourceNode <String> -SourceHead <String> -DestinationNode <String> -DestinationHead <String> [-Text <String>] -Line <String> [<CommonParameters>]
```
```PowerShell
ConvertTo-MermaidString -Key <String> -Name <String> -Shape <String> [<CommonParameters>]
```
```PowerShell
ConvertTo-MermaidString -FirstCardinality <String> -SecondCardinality <String> -Identifying <Boolean> [<CommonParameters>]
```
