Get-CMBootImage
---------------




### Synopsis
Get an OS boot image.



---


### Description

Use this cmdlet to get a Windows Preinstallation Environment (PE) OS boot image that Configuration Manager uses to deploy an OS. By default, Configuration Manager includes both x86 and x64 boot images. For more information, see Manage boot images with Configuration Manager (/mem/configmgr/osd/get-started/manage-boot-images).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMBootImage](New-CMBootImage)



* [Remove-CMBootImage](Remove-CMBootImage)



* [Set-CMBootImage](Set-CMBootImage)



* [Manage boot images with Configuration Manager](Manage boot images with Configuration Manager)





---


### Examples
#### Example 1: Get a boot image by using its ID
```PowerShell
Get-CMBootImage -Id "XYZ00002"
```

#### Example 2: List all boot images
```PowerShell
Get-CMBootImage | Select-Object PackageId, Name, ImageOSVersion, ProductionClientVersion, InputLocale | Format-Table
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

Specify a boot image ID to get. This value is a standard package ID, for example, `XYZ00002`.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **Name**

Specify the name of a boot image to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Reload**

Applies to version 2006 and later. If the version of the Windows ADK components in the boot image are out of date, use this parameter to reload this boot image with the current Windows PE version from the Windows ADK. For more information, see Update distribution points with the boot image (/mem/configmgr/osd/get-started/manage-boot-images#update-distribution-points-with-the-boot-image).






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[Switch]`|false   |named   |False        |ReloadImage|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_BootImagePackage


* IResultObject#SMS_BootImagePackage






---


### Notes
For more information on this return object and its properties, see SMS_BootImagePackage server WMI class (/mem/configmgr/develop/reference/osd/sms_bootimagepackage-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMBootImage [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Reload] [<CommonParameters>]
```
```PowerShell
Get-CMBootImage [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-Reload] [<CommonParameters>]
```
