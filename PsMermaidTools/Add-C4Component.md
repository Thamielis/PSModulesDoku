Add-MermaidC4Component
----------------------




### Synopsis
Add a component to a container boundary.



---


### Description

Add or create a component and add it to an C4 container boundary.



---


### Related Links
* [https://abbgrade.github.io/PsMermaidTools/docs/Add-MermaidC4Component.html](https://abbgrade.github.io/PsMermaidTools/docs/Add-MermaidC4Component.html)



* [https://mermaid.js.org/syntax/c4c.html#c4-component-diagram-c4component](https://mermaid.js.org/syntax/c4c.html#c4-component-diagram-c4component)





---


### Parameters
#### **Boundary**

The boundary, that the component is added to.






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[Object]`|true    |named   |true (ByValue)|



#### **Component**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **Key**

The identifier of the component.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **Name**

The component name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **Technology**

The component technology / implementation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Description**

Describes the component.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |





---


### Inputs
C4ContainerBoundary object.



---


### Outputs
* None.






---


### Syntax
```PowerShell
Add-MermaidC4Component -Boundary <Object> -Key <String> -Name <String> [-Technology <String>] [-Description <String>] [<CommonParameters>]
```
```PowerShell
Add-MermaidC4Component -Boundary <Object> [-Component] <Object> [<CommonParameters>]
```
