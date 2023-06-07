Update-CMDistributionPoint
--------------------------




### Synopsis
Update content on a distribution point.



---


### Description

Use this cmdlet to update distribution points with the latest content for clients to download.



If you manually update a distribution point, it doesn't interfere with a recurring update schedule.



For more information, see Deploy and manage content in Configuration Manager (/mem/configmgr/core/servers/deploy/configure/deploy-and-manage-content#update-content).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDistributionPoint](Get-CMDistributionPoint)



* [Set-CMDistributionPoint](Set-CMDistributionPoint)



* [Remove-CMDistributionPoint](Remove-CMDistributionPoint)



* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)



* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Get-CMOperatingSystemImage](Get-CMOperatingSystemImage)



* [Get-CMOperatingSystemInstaller](Get-CMOperatingSystemInstaller)



* [Get-CMPackage](Get-CMPackage)



* [Get-CMSoftwareUpdateDeploymentPackage](Get-CMSoftwareUpdateDeploymentPackage)



* [Invoke-CMContentValidation](Invoke-CMContentValidation)



* [Remove-CMContentDistribution](Remove-CMContentDistribution)



* [Start-CMContentDistribution](Start-CMContentDistribution)





---


### Examples
#### Example 1: Update distribution points by package name
```PowerShell
Update-CMDistributionPoint -PackageName "Package01"
```



---


### Parameters
#### **ApplicationName**

Specify the name of an application, and use the DeploymentTypeName parameter to specify the name of the deployment type with the content to update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BootImageId**

Specify the ID of a boot image to update. For example, `"XYZ00015"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BootImageName**

Specify the name of a boot image to update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeploymentTypeName**

Specify the name of an application deployment type to update its content. Use the ApplicationName parameter to specify the application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DriverPackageId**

Specify the ID of a driver package to update. For example, `"XYZ00017"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DriverPackageName**

Specify the name of a driver package to update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an object type to update. To get these objects, use one of the following cmdlets:


* Get-CMPackage (Get-CMPackage.md)for a legacy package - Get-CMBootImage (Get-CMBootImage.md)for a boot image - Get-CMDeploymentPackage (Get-CMDeploymentPackage.md)for a software update deployment package - Get-CMDriverPackage (Get-CMDriverPackage.md)for a driver package - Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)for an OS image - Get-CMOperatingSystemInstaller (Get-CMOperatingSystemInstaller.md)for an OS upgrade package






|Type             |Required|Position|PipelineInput |Aliases                                                                                                                          |
|-----------------|--------|--------|--------------|---------------------------------------------------------------------------------------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|BootImage<br/>DriverPackage<br/>OperatingSystemImage<br/>OperatingSystemInstaller<br/>Package<br/>SoftwareUpdateDeploymentPackage|



#### **ManifestPath**

Specify the UNC path of a Microsoft App-V virtual application's XML manifest file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OperatingSystemImageId**

Specify the ID of an OS image to update. For example, `"XYZ00018"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **OperatingSystemImageName**

Specify the name of an OS image to update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **OperatingSystemInstallerId**

Specify the ID of an OS upgrade package to update. For example, `"XYZ00019"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **OperatingSystemInstallerName**

Specify the name of an OS upgrade package to update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageId**

Specify the ID of a legacy package to update. For example, `"XYZ00020"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageName**

Specify the name of a legacy package to update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ReloadBootImage**

When you update a boot image, add this parameter to reload it with the current Windows PE version from the Windows ADK. For more information, see Manage boot images in Configuration Manager (/mem/configmgr/osd/get-started/manage-boot-images#update-distribution-points-with-the-boot-image).






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[Switch]`|false   |named   |False        |Reload |



#### **SoftwareUpdateDeploymentPackageId**

Specify the ID of a software update deployment package to update. For example, `"XYZ00016"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateDeploymentPackageName**

Specify the name of a software update deployment package to update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Update-CMDistributionPoint -ApplicationName <String> -DeploymentTypeName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ManifestPath <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint -BootImageId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ReloadBootImage] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint -BootImageName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-ReloadBootImage] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] -DriverPackageId <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] -DriverPackageName <String> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-ReloadBootImage] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemImageId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemImageName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemInstallerId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -OperatingSystemInstallerName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateDeploymentPackageId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -SoftwareUpdateDeploymentPackageName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
