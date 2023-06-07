Remove-CMContentDistribution
----------------------------




### Synopsis
Remove packages from a distribution point.



---


### Description

Use this cmdlet to remove one or more packages from a distribution point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplication](Get-CMApplication)



* [Get-CMBootImage](Get-CMBootImage)



* [Get-CMDeploymentPackage](Get-CMDeploymentPackage)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Get-CMOperatingSystemImage](Get-CMOperatingSystemImage)



* [Get-CMOperatingSystemInstaller](Get-CMOperatingSystemInstaller)



* [Get-CMPackage](Get-CMPackage)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [Invoke-CMContentValidation](Invoke-CMContentValidation)



* [Start-CMContentDistribution](Start-CMContentDistribution)



* [Update-CMDistributionPoint](Update-CMDistributionPoint)





---


### Examples
#### Example 1: Remove a driver package from a distribution point
```PowerShell
Remove-CMContentDistribution -DriverPackageID "PCP00019" -DistributionPointName "distribution-server.contoso.com"
```



---


### Parameters
#### **ApplicationId**

Specify an array of application IDs to remove. These IDs are GUIDs as strings.


By default, Configuration Manager also removes the content for dependent applications. To disable this behavior, use the DisableContentDependencyDetection parameter.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **ApplicationName**

Specify an array of application names to remove.


By default, Configuration Manager also removes the content for dependent applications. To disable this behavior, use the DisableContentDependencyDetection parameter.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **BootImageId**

Specify an array of boot image IDs to remove. For example, `"XYZ00015"`.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|true    |named   |False        |BootImageIds|



#### **BootImageName**

Specify an array of boot image names to remove.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|true    |named   |False        |BootImageNames|



#### **CollectionName**

Specify an array of Configuration Manager collection names. Use this collection to target the distribution points from which to remove the content.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **DeploymentPackageId**

Specify an array of software update deployment package IDs to remove. For example, `"XYZ00016"`.






|Type        |Required|Position|PipelineInput|Aliases                                                                        |
|------------|--------|--------|-------------|-------------------------------------------------------------------------------|
|`[String[]]`|true    |named   |False        |DeploymentPackageIds<br/>SoftwareUpdatesPackageId<br/>SoftwareUpdatesPackageIds|



#### **DeploymentPackageName**

Specify an array of software update deployment package names to remove.






|Type        |Required|Position|PipelineInput|Aliases                                                                              |
|------------|--------|--------|-------------|-------------------------------------------------------------------------------------|
|`[String[]]`|true    |named   |False        |DeploymentPackageNames<br/>SoftwareUpdatesPackageName<br/>SoftwareUpdatesPackageNames|



#### **DisableContentDependencyDetection**

Add this parameter to not automatically remove content for dependent apps.






|Type      |Required|Position|PipelineInput|Aliases                                   |
|----------|--------|--------|-------------|------------------------------------------|
|`[Switch]`|false   |named   |False        |DisableDetectAssociatedContentDependencies|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPointGroupName**

Specify an array of distribution point group names from which to remove the content.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **DistributionPointName**

Specify an array of distribution point names from which to remove the content.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **DriverPackageId**

Specify an array of driver package IDs to remove. For example, `"XYZ00017"`.






|Type        |Required|Position|PipelineInput|Aliases         |
|------------|--------|--------|-------------|----------------|
|`[String[]]`|true    |named   |False        |DriverPackageIds|



#### **DriverPackageName**

Specify an array of driver package names to remove.






|Type        |Required|Position|PipelineInput|Aliases           |
|------------|--------|--------|-------------|------------------|
|`[String[]]`|true    |named   |False        |DriverPackageNames|



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an object type to remove. To get these objects, use one of the following cmdlets:


* Get-CMApplication (Get-CMApplication.md)for an application - Get-CMPackage (Get-CMPackage.md)for a legacy package - Get-CMBootImage (Get-CMBootImage.md)for a boot image - Get-CMDeploymentPackage (Get-CMDeploymentPackage.md)for a software update deployment package - Get-CMSoftwareUpdateGroup (Get-CMSoftwareUpdateGroup.md)for the content in a software update group - Get-CMDriverPackage (Get-CMDriverPackage.md)for a driver package - Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)for an OS image - Get-CMOperatingSystemInstaller (Get-CMOperatingSystemInstaller.md)for an OS upgrade package - Get-CMTaskSequence (Get-CMTaskSequence.md)for the content referenced by a task sequence






|Type             |Required|Position|PipelineInput |Aliases                                                                                                                                                               |
|-----------------|--------|--------|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Application<br/>Package<br/>BootImage<br/>DeploymentPackage<br/>SoftwareUpdatePackage<br/>DriverPackage<br/>ImagePackage<br/>OperatingSystemInstaller<br/>TaskSequence|



#### **OperatingSystemImage**

Specify an OS image object to remove. To get this object, use the Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **OperatingSystemImageId**

Specify an array of OS image IDs to remove. For example, `"XYZ00018"`.






|Type        |Required|Position|PipelineInput|Aliases                |
|------------|--------|--------|-------------|-----------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemImageIds|



#### **OperatingSystemImageName**

Specify an array of OS image names to remove.






|Type        |Required|Position|PipelineInput|Aliases                  |
|------------|--------|--------|-------------|-------------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemImageNames|



#### **OperatingSystemInstallerId**

Specify an array of OS upgrade package IDs to remove. For example, `"XYZ00019"`.






|Type        |Required|Position|PipelineInput|Aliases                    |
|------------|--------|--------|-------------|---------------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemInstallerIds|



#### **OperatingSystemInstallerName**

Specify an array of OS upgrade package names to remove.






|Type        |Required|Position|PipelineInput|Aliases                           |
|------------|--------|--------|-------------|----------------------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemImageInstallerNames|



#### **PackageId**

Specify an array of legacy package IDs to remove. For example, `"XYZ00020"`.






|Type        |Required|Position|PipelineInput|Aliases   |
|------------|--------|--------|-------------|----------|
|`[String[]]`|true    |named   |False        |PackageIds|



#### **PackageName**

Specify an array of legacy package names to remove.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|true    |named   |False        |PackageNames|



#### **TaskSequenceId**

Specify an array of task sequence IDs to remove referenced content. For example, `"XYZ00021"`.






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|true    |named   |False        |TaskSequenceIds|



#### **TaskSequenceName**

Specify an array of task sequence names to remove referenced content.






|Type        |Required|Position|PipelineInput|Aliases          |
|------------|--------|--------|-------------|-----------------|
|`[String[]]`|true    |named   |False        |TaskSequenceNames|



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
Remove-CMContentDistribution -ApplicationId <String[]> [-CollectionName <String[]>] [-DisableContentDependencyDetection] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution -ApplicationName <String[]> [-CollectionName <String[]>] [-DisableContentDependencyDetection] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution -BootImageId <String[]> [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution -BootImageName <String[]> [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] -DeploymentPackageId <String[]> [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] -DeploymentPackageName <String[]> [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableContentDependencyDetection] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] -DriverPackageId <String[]> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] -DriverPackageName <String[]> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] -OperatingSystemImage <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] -OperatingSystemImageId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] -OperatingSystemImageName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] -OperatingSystemInstallerId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] -OperatingSystemInstallerName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] -PackageId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] -PackageName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] -TaskSequenceId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-Force] [-ForceWildcardHandling] -TaskSequenceName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
