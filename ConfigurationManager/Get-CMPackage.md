Get-CMPackage
-------------




### Synopsis
Get a Configuration Manager legacy package.



---


### Description

The Get-CMPackage cmdlet gets a Configuration Manager legacy package. Configuration Manager current branch continues to support packages and programs that were used in Configuration Manager 2007. For more information, see Packages and programs in Configuration Manager (/mem/configmgr/apps/deploy-use/packages-and-programs).



Other objects are considered "packages" in certain contexts, but you need to use other cmdlets to get them. For more information, see the Related links (#related-links).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMPackage](Export-CMPackage)



* [Import-CMPackage](Import-CMPackage)



* [New-CMPackage](New-CMPackage)



* [Remove-CMPackage](Remove-CMPackage)



* [Set-CMPackage](Set-CMPackage)



* [Get-CMProgram](Get-CMProgram)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Get-CMSoftwareUpdateDeploymentPackage](Get-CMSoftwareUpdateDeploymentPackage)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [Get-CMApplication](Get-CMApplication)





---


### Examples
#### Example 1: Get all packages
```PowerShell
$packages = Get-CMPackage -PackageType RegularPackage
```

#### Example 2: Get a package by using an ID
```PowerShell
Get-CMPackage -Id "CM100002"
```

#### Example 3: Get a package by using a name
```PowerShell
Get-CMPackage -Name "Configuration Manager Client Package"
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

Specifies the package ID to get. For example, `"CM100002"`.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **Name**

Specifies the name of a package to get. For example, `"Configuration Manager Client Package"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PackageType**

Specify a type of package to filter the result.



Valid Values:

* RegularPackage
* Driver
* TaskSequence
* SoftwareUpdate
* VirtualAppPackage
* ContentPackage
* ImageDeployment
* BootImage
* OSInstallPackage






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[PackageType]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_Package


* IResultObject#SMS_Package






---


### Notes
For more information on this return object and its properties, see SMS_Package server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_package-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMPackage [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -Id <String> [-PackageType {RegularPackage | Driver | TaskSequence | SoftwareUpdate | ContentPackage | ImageDeployment | BootImage | OSInstallPackage}] [<CommonParameters>]
```
```PowerShell
Get-CMPackage [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [-PackageType {RegularPackage | Driver | TaskSequence | SoftwareUpdate | ContentPackage | ImageDeployment | BootImage | OSInstallPackage}] [<CommonParameters>]
```
