Get-CMBaselineXMLDefinition
---------------------------




### Synopsis
Gets the XML definition of a configuration baseline.



---


### Description

The Get-CMBaselineXMLDefinition cmdlet gets and displays the XML definition of one or more baseline configurations.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBaseline](Get-CMBaseline)





---


### Examples
#### Example 1: Get a configuration baseline XML definition
```PowerShell
PS XYZ:\> $CIObj = Get-CMBaseline -Id "16777568"
PS XYZ:\> Get-CMBaselineXMLDefinition -InputObject $CIObj
```
The first command gets the configuration baseline object that has the ID 16777568, and stores the object in the $CIObj variable.


The second command gets the XML definition of the configuration baseline stored in $CIObj.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of IDs of baseline configurations.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a CMBaseline object. To obtain a CMBaseline object, use the Get-CMBaseline (Get-CMBaseline.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies an array of baseline configuration names.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |0       |False        |LocalizedDisplayName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [String](https://learn.microsoft.com/en-us/dotnet/api/System.String)


* [String[]](https://learn.microsoft.com/en-us/dotnet/api/System.String[])






---


### Notes




---


### Syntax
```PowerShell
Get-CMBaselineXMLDefinition [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMBaselineXMLDefinition [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMBaselineXMLDefinition [[-Name] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
