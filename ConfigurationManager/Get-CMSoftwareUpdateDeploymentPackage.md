Get-CMSoftwareUpdateDeploymentPackage
-------------------------------------




### Synopsis
Get a software update deployment package.



---


### Description

Use this cmdlet to get a deployment package for a software update. A software update deployment package object contains one or more software updates.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMSoftwareUpdateDeploymentPackage](New-CMSoftwareUpdateDeploymentPackage)



* [Remove-CMSoftwareUpdateDeploymentPackage](Remove-CMSoftwareUpdateDeploymentPackage)



* [Set-CMSoftwareUpdateDeploymentPackage](Set-CMSoftwareUpdateDeploymentPackage)



* [Remove-CMSoftwareUpdateFromPackage](Remove-CMSoftwareUpdateFromPackage)





---


### Examples
#### Example 1: Get a deployment package by using a name
```PowerShell
Get-CMSoftwareUpdateDeploymentPackage -Name "Asdset"
```

#### Example 2: Get a deployment package by using an ID
```PowerShell
Get-CMSoftwareUpdateDeploymentPackage -Id "ST10000C"
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

Specify a package ID for the deployment package to get. This value is a standard package ID, for example `XYZ0035C`.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **Name**

Specify the name of the deployment package to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SoftwareUpdatesPackage


* IResultObject#SMS_SoftwareUpdatesPackage






---


### Notes
For more information on this return object and its properties, see SMS_SoftwareUpdatesPackage server WMI class (/mem/configmgr/develop/reference/sum/sms_softwareupdatespackage-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMSoftwareUpdateDeploymentPackage [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdateDeploymentPackage [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
