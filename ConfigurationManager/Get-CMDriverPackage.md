Get-CMDriverPackage
-------------------




### Synopsis
Get a driver package.



---


### Description

Use this cmdlet to get a driver package. Group similar device drivers in packages to help streamline OS deployments. For example, create a driver package for each computer manufacturer on your network. For more information, see Manage drivers in Configuration Manager (/mem/configmgr/osd/get-started/manage-drivers).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMDriverPackage](Export-CMDriverPackage)



* [Import-CMDriverPackage](Import-CMDriverPackage)



* [New-CMDriverPackage](New-CMDriverPackage)



* [Remove-CMDriverPackage](Remove-CMDriverPackage)



* [Set-CMDriverPackage](Set-CMDriverPackage)



* [Get-CMDriver](Get-CMDriver)



* [Manage drivers in Configuration Manager](Manage drivers in Configuration Manager)





---


### Examples
#### Example 1: Get a driver package by ID
```PowerShell
Get-CMDriverPackage -Id "XYZ00042" -Fast
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify an array of IDs for a driver package. This value is a standard package ID format, for example, `XYZ00204`.






|Type        |Required|Position|PipelineInput|Aliases  |
|------------|--------|--------|-------------|---------|
|`[String[]]`|true    |named   |False        |PackageId|



#### **Name**

Specify the name of a driver package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_DriverPackage


* IResultObject#SMS_DriverPackage






---


### Notes
For more information on this return object and its properties, see SMS_DriverPackage server WMI class (/mem/configmgr/develop/reference/osd/sms_driverpackage-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMDriverPackage [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -Id <String[]> [<CommonParameters>]
```
```PowerShell
Get-CMDriverPackage [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
