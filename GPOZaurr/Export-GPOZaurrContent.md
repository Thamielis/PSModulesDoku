Export-GPOZaurrContent
----------------------




### Synopsis
Saves GPOs to XML or HTML files.



---


### Description

Saves GPOs to XML or HTML files.



---


### Examples
#### EXAMPLE 1
```PowerShell
An example
```



---


### Parameters
#### **FolderOutput**

The folder where the GPOs will be saved.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |1       |false        |Path   |



#### **ReportType**

The type of report to generate. Valid values are XML or HTML. Default is XML.



Valid Values:

* XML
* HTML






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
Export-GPOZaurrContent [-FolderOutput] <String> [[-ReportType] <String>] [<CommonParameters>]
```
