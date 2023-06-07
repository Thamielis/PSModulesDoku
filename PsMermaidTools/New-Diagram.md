New-MermaidDiagram
------------------




### Synopsis
Creates a new mermaid diagram.



---


### Description

Creates and returns a new diagram definition, that can be populated and later exported.



---


### Related Links
* [https://mermaid-js.github.io/mermaid/#/README?id=diagram-types](https://mermaid-js.github.io/mermaid/#/README?id=diagram-types)





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
#### **Flowchart**

The mermaid diagram type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |1       |false        |



#### **ErDiagram**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |1       |false        |



#### **C4Component**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |1       |false        |



#### **Orientation**

The diagram orientation.



Valid Values:

* top-to-bottom
* top-down
* bottom-to-top
* right-to-left
* left-to-right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |2       |false        |





---


### Inputs
None.



---


### Outputs
* Mermaid diagram definition object.






---


### Syntax
```PowerShell
New-MermaidDiagram [-ErDiagram] [<CommonParameters>]
```
```PowerShell
New-MermaidDiagram [-Flowchart] [-Orientation] <String> [<CommonParameters>]
```
```PowerShell
New-MermaidDiagram [-C4Component] [<CommonParameters>]
```
