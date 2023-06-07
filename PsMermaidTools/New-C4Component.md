New-MermaidC4Component
----------------------




### Synopsis
Create a component.



---


### Description

Create a component for a C4 diagram. It can be edited and referenced.



---


### Related Links
* [https://abbgrade.github.io/PsMermaidTools/docs/New-MermaidC4Component.html](https://abbgrade.github.io/PsMermaidTools/docs/New-MermaidC4Component.html)



* [https://mermaid.js.org/syntax/c4c.html#c4-component-diagram-c4component](https://mermaid.js.org/syntax/c4c.html#c4-component-diagram-c4component)





---


### Parameters
#### **Key**

The identifier of the component.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **Name**

The component name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |2       |false        |



#### **Technology**

The component technology / implementation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |3       |false        |



#### **Description**

Describes the component.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |4       |false        |





---


### Outputs
* None.






---


### Syntax
```PowerShell
New-MermaidC4Component [-Key] <String> [-Name] <String> [[-Technology] <String>] [[-Description] <String>] [<CommonParameters>]
```
