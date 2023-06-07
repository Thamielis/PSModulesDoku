Get-CMSoftwareMeteringSetting
-----------------------------




### Synopsis
Gets Configuration Manager software metering settings.



---


### Description

The Get-CMSoftwareMeteringSetting cmdlet gets a software metering settings object in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMSoftwareMeteringSetting](Set-CMSoftwareMeteringSetting)





---


### Examples
#### Example 1: Get software metering setting object
```PowerShell
PS XYZ:\> Get-CMSoftwareMeteringSetting

ClientComponentName : Software Metering Agent
FileType            : 2
Flags               : 1
ItemName            : Software Metering Agent
ItemType            : Client Component
PropLists           :
Props               :
RegMultiStringLists :
SiteCode            : CM1
```
This command gets a software metering setting object.


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





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_ClientComp


* IResultObject#SMS_SCI_ClientComp






---


### Notes




---


### Syntax
```PowerShell
Get-CMSoftwareMeteringSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
