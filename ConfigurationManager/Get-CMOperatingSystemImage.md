Get-CMOperatingSystemImage
--------------------------




### Synopsis
Gets OS images.



---


### Description

The Get-CMOperatingSystemImage cmdlet gets one or more OS images on a Configuration Manager site. OS images are .wim format files and represent a compressed collection of reference files and folders that Configuration Manager requires to successfully install and configure an OS on a computer.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMOperatingSystemImage](New-CMOperatingSystemImage)



* [Set-CMOperatingSystemImage](Set-CMOperatingSystemImage)



* [Remove-CMOperatingSystemImage](Remove-CMOperatingSystemImage)



* [Get-CMOperatingSystemImageUpdateSchedule](Get-CMOperatingSystemImageUpdateSchedule)





---


### Examples
#### Example 1: Get an OS image
```PowerShell
Get-CMOperatingSystemImage -Name "OSImagePkg01" -SecuredScopeNames "SecScope02"
```



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

Specifies an array of IDs of OS images.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **Name**

Specifies the name of an OS image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Reload**

Applies to version 2006 and later. If you change the image properties using an external tool, use this option to reload the information in the site database.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[Switch]`|false   |named   |False        |ReloadImage|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_ImagePackage


* IResultObject#SMS_ImagePackage






---


### Notes




---


### Syntax
```PowerShell
Get-CMOperatingSystemImage [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Reload] [<CommonParameters>]
```
```PowerShell
Get-CMOperatingSystemImage [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-Reload] [<CommonParameters>]
```
