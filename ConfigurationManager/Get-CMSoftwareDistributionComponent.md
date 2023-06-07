Get-CMSoftwareDistributionComponent
-----------------------------------




### Synopsis
Gets an object that represents a software distribution component in Configuration Manager.



---


### Description

The Get-CMSoftwareDistributionComponent cmdlet gets an object that represents a software distribution component in Configuration Manager. A software distribution component consists of individual components such as the client software distribution component.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMSoftwareDistributionComponent](Set-CMSoftwareDistributionComponent)





---


### Examples
#### Example 1: Get a software distribution component
```PowerShell
PS XYZ:\> Get-CMSoftwareDistributionComponent -Name "CM2"
```
This command gets the software distribution component.


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



#### **SiteCode**

Specifies a site code of a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies an array of site system server names.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Get-CMSoftwareDistributionComponent [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [-SiteSystemServerName <String[]>] [<CommonParameters>]
```
