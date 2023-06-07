Get-OfficeExcel
---------------




### Synopsis

Get-OfficeExcel [-FilePath] <string> [[-RecalculateAllFormulas] <bool>] [[-EventTracking] <XLEventTracking>] [-Template] [<CommonParameters>]




---


### Description


---


### Parameters
#### **EventTracking**

Valid Values:

* Enabled
* Disabled






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[XLEventTracking]`|false   |2       |false        |



#### **FilePath**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |0       |false        |



#### **RecalculateAllFormulas**




|Type    |Required|Position|PipelineInput|
|--------|--------|--------|-------------|
|`[bool]`|false   |1       |false        |



#### **Template**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |





---


### Inputs
None




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
{@{name=Get-OfficeExcel; CommonParameters=True; parameter=System.Object[]}}
```
