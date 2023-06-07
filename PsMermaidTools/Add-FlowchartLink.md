Add-MermaidFlowchartLink
------------------------




### Synopsis

Add-MermaidFlowchartLink [-Source] <string> [-Destination] <string> [[-Text] <string>] [-Diagram <Object>] [-Line <string>] [-DestinationHead <string>] [-SourceHead <string>] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Destination**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |1       |false        |



#### **DestinationHead**

Valid Values:

* arrow
* open
* circle
* cross






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |Named   |false        |



#### **Diagram**




|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[Object]`|false   |Named   |true (ByValue)|



#### **Line**

Valid Values:

* solid
* dotted
* thick






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |Named   |false        |



#### **Source**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |0       |false        |



#### **SourceHead**

Valid Values:

* arrow
* open
* circle
* cross






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |Named   |false        |



#### **Text**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |2       |false        |





---


### Inputs
System.Object




---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Syntax
```PowerShell
syntaxItem
```
```PowerShell
----------
```
```PowerShell
{@{name=Add-MermaidFlowchartLink; CommonParameters=True; parameter=System.Object[]}}
```
