Start-CMContentDistribution
---------------------------




### Synopsis
Distribute content to distribution points.



---


### Description

Use this cmdlet to distribute content from the content library on the site server to distribution points.



You can use this cmdlet to distribute content for the following deployable objects:



- Applications



- Legacy packages



- Software update deployment packages



- Driver packages



- OS images



- OS upgrade packages



- Boot images



- Content referenced by task sequences






You can distribute the content to distribution points, distribution point groups, or collections associated with distribution point groups.



For more information, see Deploy and manage content in Configuration Manager (/mem/configmgr/core/servers/deploy/configure/deploy-and-manage-content).


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



* [Remove-CMContentDistribution](Remove-CMContentDistribution)



* [Invoke-CMContentValidation](Invoke-CMContentValidation)



* [Update-CMDistributionPoint](Update-CMDistributionPoint)





---


### Examples
#### Example 1: Distribute a boot image
```PowerShell
Start-CMContentDistribution -BootImageId "CM200004" -DistributionPointName "CMDIV-TSQA04.CORP.CONTOSO.COM"
```



---


### Parameters
#### **ApplicationId**

Specify an array of application IDs to distribute. These IDs are GUIDs as strings.


By default, Configuration Manager also distributes the content for dependent applications. To disable this behavior, use the DisableContentDependencyDetection parameter.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **ApplicationName**

Specify an array of application names to distribute.


By default, Configuration Manager also distributes the content for dependent applications. To disable this behavior, use the DisableContentDependencyDetection parameter.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **BootImageId**

Specify an array of boot image IDs to distribute. For example, `"XYZ00015"`.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|true    |named   |False        |BootImageIds|



#### **BootImageName**

Specify an array of boot image names to distribute.






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|true    |named   |False        |BootImageNames|



#### **CollectionName**

Specify an array of Configuration Manager collection names. Use this collection to target the distribution points to which to distribute the content.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **DeploymentPackageId**

Specify an array of software update deployment package IDs to distribute. For example, `"XYZ00016"`.






|Type        |Required|Position|PipelineInput|Aliases                                                                        |
|------------|--------|--------|-------------|-------------------------------------------------------------------------------|
|`[String[]]`|true    |named   |False        |DeploymentPackageIds<br/>SoftwareUpdatesPackageId<br/>SoftwareUpdatesPackageIds|



#### **DeploymentPackageName**

Specify an array of software update deployment package names to distribute.






|Type        |Required|Position|PipelineInput|Aliases                                                                              |
|------------|--------|--------|-------------|-------------------------------------------------------------------------------------|
|`[String[]]`|true    |named   |False        |DeploymentPackageNames<br/>SoftwareUpdatesPackageName<br/>SoftwareUpdatesPackageNames|



#### **DisableContentDependencyDetection**

Add this parameter to not automatically distribute content for dependent apps.






|Type      |Required|Position|PipelineInput|Aliases                                   |
|----------|--------|--------|-------------|------------------------------------------|
|`[Switch]`|false   |named   |False        |DisableDetectAssociatedContentDependencies|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPointGroupName**

Specify an array of distribution point group names to which to distribute the content.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **DistributionPointName**

Specify an array of distribution point names to which to distribute the content.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **DriverPackageId**

Specify an array of driver package IDs to distribute. For example, `"XYZ00017"`.






|Type        |Required|Position|PipelineInput|Aliases         |
|------------|--------|--------|-------------|----------------|
|`[String[]]`|true    |named   |False        |DriverPackageIds|



#### **DriverPackageName**

Specify an array of driver package names to distribute.






|Type        |Required|Position|PipelineInput|Aliases           |
|------------|--------|--------|-------------|------------------|
|`[String[]]`|true    |named   |False        |DriverPackageNames|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an object type to distribute. To get these objects, use one of the following cmdlets:


* Get-CMApplication (Get-CMApplication.md)for an application - Get-CMPackage (Get-CMPackage.md)for a legacy package - Get-CMBootImage (Get-CMBootImage.md)for a boot image - Get-CMDeploymentPackage (Get-CMDeploymentPackage.md)for a software update deployment package - Get-CMSoftwareUpdateGroup (Get-CMSoftwareUpdateGroup.md)for the content in a software update group - Get-CMDriverPackage (Get-CMDriverPackage.md)for a driver package - Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)for an OS image - Get-CMOperatingSystemInstaller (Get-CMOperatingSystemInstaller.md)for an OS upgrade package - Get-CMTaskSequence (Get-CMTaskSequence.md)for the content referenced by a task sequence






|Type             |Required|Position|PipelineInput |Aliases                                                                                                                                                               |
|-----------------|--------|--------|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Application<br/>Package<br/>BootImage<br/>DeploymentPackage<br/>SoftwareUpdatePackage<br/>DriverPackage<br/>ImagePackage<br/>OperatingSystemInstaller<br/>TaskSequence|



#### **OperatingSystemImage**

Specify an OS image object to distribute. To get this object, use the Get-CMOperatingSystemImage (Get-CMOperatingSystemImage.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **OperatingSystemImageId**

Specify an array of OS image IDs to distribute. For example, `"XYZ00018"`.






|Type        |Required|Position|PipelineInput|Aliases                |
|------------|--------|--------|-------------|-----------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemImageIds|



#### **OperatingSystemImageName**

Specify an array of OS image names to distribute.






|Type        |Required|Position|PipelineInput|Aliases                  |
|------------|--------|--------|-------------|-------------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemImageNames|



#### **OperatingSystemInstallerId**

Specify an array of OS upgrade package IDs to distribute. For example, `"XYZ00019"`.






|Type        |Required|Position|PipelineInput|Aliases                    |
|------------|--------|--------|-------------|---------------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemInstallerIds|



#### **OperatingSystemInstallerName**

Specify an array of OS upgrade package names to distribute.






|Type        |Required|Position|PipelineInput|Aliases                           |
|------------|--------|--------|-------------|----------------------------------|
|`[String[]]`|true    |named   |False        |OperatingSystemImageInstallerNames|



#### **PackageId**

Specify an array of legacy package IDs to distribute. For example, `"XYZ00020"`.






|Type        |Required|Position|PipelineInput|Aliases   |
|------------|--------|--------|-------------|----------|
|`[String[]]`|true    |named   |False        |PackageIds|



#### **PackageName**

Specify an array of legacy package names to distribute.






|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[String[]]`|true    |named   |False        |PackageNames|



#### **TaskSequenceId**

Specify an array of task sequence IDs to distribute referenced content. For example, `"XYZ00021"`.






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|true    |named   |False        |TaskSequenceIds|



#### **TaskSequenceName**

Specify an array of task sequence names to distribute referenced content.






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
Start-CMContentDistribution -ApplicationId <String[]> [-CollectionName <String[]>] [-DisableContentDependencyDetection] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution -ApplicationName <String[]> [-CollectionName <String[]>] [-DisableContentDependencyDetection] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution -BootImageId <String[]> [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution -BootImageName <String[]> [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] -DeploymentPackageId <String[]> [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] -DeploymentPackageName <String[]> [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableContentDependencyDetection] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] -DriverPackageId <String[]> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] -DriverPackageName <String[]> [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] -OperatingSystemImage <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] -OperatingSystemImageId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] -OperatingSystemImageName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] -OperatingSystemInstallerId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] -OperatingSystemInstallerName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] -PackageId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] -PackageName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] -TaskSequenceId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMContentDistribution [-CollectionName <String[]>] [-DisableWildcardHandling] [-DistributionPointGroupName <String[]>] [-DistributionPointName <String[]>] [-ForceWildcardHandling] -TaskSequenceName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
