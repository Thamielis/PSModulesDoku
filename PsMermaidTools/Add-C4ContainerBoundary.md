Add-MermaidC4ContainerBoundary
------------------------------




### Synopsis
Add a container boundary to a diagram.



---


### Description

Add or create a container boundary and add it to an C4 diagram.



---


### Related Links
* [https://abbgrade.github.io/PsMermaidTools/docs/Add-MermaidC4ContainerBoundary.html](https://abbgrade.github.io/PsMermaidTools/docs/Add-MermaidC4ContainerBoundary.html)



* [https://mermaid.js.org/syntax/c4c.html#c4-component-diagram-c4component](https://mermaid.js.org/syntax/c4c.html#c4-component-diagram-c4component)





---


### Parameters
#### **Diagram**

The diagram, that the container is added to.






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[Object]`|true    |named   |true (ByValue)|



#### **ContainerBoundary**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **Key**

The identifier of the container.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |



#### **Name**

The container name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |false        |





---


### Inputs
C4Component diagram object.



---


### Outputs
* None.






---


### Syntax
```PowerShell
Add-MermaidC4ContainerBoundary -Diagram <Object> -Key <String> -Name <String> [<CommonParameters>]
```
```PowerShell
Add-MermaidC4ContainerBoundary -Diagram <Object> [-ContainerBoundary] <Object> [<CommonParameters>]
```
