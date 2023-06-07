Get-CMOperatingSystemInstaller
------------------------------




### Synopsis
Gets OS upgrade packages.



---


### Description

The Get-CMOperatingSystemInstaller cmdlet gets one or more OS upgrade packages. An OS upgrade package contains all the files that Configuration Manager needs to install a Windows OS on a reference computer.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMOperatingSystemInstaller](New-CMOperatingSystemInstaller)



* [Remove-CMOperatingSystemInstaller](Remove-CMOperatingSystemInstaller)



* [Set-CMOperatingSystemInstaller](Set-CMOperatingSystemInstaller)





---


### Examples
#### Example 1: Get an OS upgrade package
```PowerShell
Get-CMOperatingSystemInstaller -Name "OSInstPkg01"-SecuredScopeNames "SecScope02"
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

Specifies an array of IDs of OS upgrade packages.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **Name**

Specifies the name of an OS upgrade package.






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
* IResultObject[]#SMS_OperatingSystemInstallPackage


* IResultObject#SMS_OperatingSystemInstallPackage






---


### Notes




---


### Syntax
```PowerShell
Get-CMOperatingSystemInstaller [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Reload] [<CommonParameters>]
```
```PowerShell
Get-CMOperatingSystemInstaller [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-Reload] [<CommonParameters>]
```
