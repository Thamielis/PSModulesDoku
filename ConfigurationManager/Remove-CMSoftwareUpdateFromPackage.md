Remove-CMSoftwareUpdateFromPackage
----------------------------------




### Synopsis
Remove an update from a software update package.



---


### Description

Use this cmdlet to remove the specified software update from a package.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateDeploymentPackage](Get-CMSoftwareUpdateDeploymentPackage)



* [New-CMSoftwareUpdateDeploymentPackage](New-CMSoftwareUpdateDeploymentPackage)



* [Set-CMSoftwareUpdateDeploymentPackage](Set-CMSoftwareUpdateDeploymentPackage)



* [Remove-CMSoftwareUpdateDeploymentPackage](Remove-CMSoftwareUpdateDeploymentPackage)



* [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate)



* [Save-CMSoftwareUpdate](Save-CMSoftwareUpdate)





---


### Examples
#### Example 1: Remove an update and refresh the content
```PowerShell
$SU0 = "Bing Bar 7.1 (KB2673770)"
$SU0_ID = ( Get-CMSoftwareUpdate -Name $SU0 -Fast ).CI_ID

$suppkg1 = Get-CMSoftwareUpdateDeploymentPackage -Id "XYZ0000C"

Remove-CMSoftwareUpdateFromPackage -SoftwareUpdatePackageId $suppkg1.PackageID -SoftwareUpdateId $SU0_ID -RefreshDistributionPoint -Force
```

#### Example 2: Remove two updates but don't refresh the content
```PowerShell
$SU1 = "Bing Bar 7.1 (KB2673771)"
$SU2 = "Bing Bar 7.1 (KB2673772)"

$suppkg1 = Get-CMSoftwareUpdateDeploymentPackage -Id "XYZ0000C"

Remove-CMSoftwareUpdateFromPackage -SoftwareUpdatePackage $suppkg1 -SoftwareUpdateName ($SU1, $SU2)
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Add this parameter to run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RefreshDistributionPoint**

Add this parameter to update the package content on the distribution points. If you don't include this parameter, you need to manually update distribution points. For more information, see Manage distributed content (/mem/configmgr/core/servers/deploy/configure/deploy-and-manage-content#bkmk_manage).






|Type      |Required|Position|PipelineInput|Aliases                                                     |
|----------|--------|--------|-------------|------------------------------------------------------------|
|`[Switch]`|false   |named   |False        |RefreshDistributionPointAfterRemoveSoftwareUpdateFromPackage|



#### **SoftwareUpdate**

Specify an array of software update objects to remove from the package. To get this object, use the Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)cmdlet.






|Type               |Required|Position|PipelineInput |Aliases        |
|-------------------|--------|--------|--------------|---------------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|SoftwareUpdates|



#### **SoftwareUpdateId**

Specify an array of IDs for software updates to remove from the package. This value is the CI_ID of the update, for example `1584792`.






|Type        |Required|Position|PipelineInput|Aliases          |
|------------|--------|--------|-------------|-----------------|
|`[String[]]`|true    |named   |False        |SoftwareUpdateIds|



#### **SoftwareUpdateName**

Specify an array of names for software updates to remove from the package.






|Type        |Required|Position|PipelineInput|Aliases            |
|------------|--------|--------|-------------|-------------------|
|`[String[]]`|true    |named   |False        |SoftwareUpdateNames|



#### **SoftwareUpdatePackage**

Specify a software update package object from which to remove the updates. To get this object, use the Get-CMSoftwareUpdateDeploymentPackage (Get-CMSoftwareUpdateDeploymentPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SoftwareUpdatePackageId**

Specify a software update package ID from which to remove the updates. This value is a standard package ID, for example `XYZ0035E`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdatePackageName**

Specify a software update package name from which to remove the updates.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]



Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMSoftwareUpdateFromPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RefreshDistributionPoint] -SoftwareUpdate <IResultObject[]> -SoftwareUpdatePackageId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RefreshDistributionPoint] -SoftwareUpdate <IResultObject[]> -SoftwareUpdatePackageName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RefreshDistributionPoint] -SoftwareUpdate <IResultObject[]> -SoftwareUpdatePackage <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RefreshDistributionPoint] -SoftwareUpdateId <String[]> -SoftwareUpdatePackageId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RefreshDistributionPoint] -SoftwareUpdateId <String[]> -SoftwareUpdatePackageName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RefreshDistributionPoint] -SoftwareUpdateId <String[]> -SoftwareUpdatePackage <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RefreshDistributionPoint] -SoftwareUpdateName <String[]> -SoftwareUpdatePackageId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RefreshDistributionPoint] -SoftwareUpdateName <String[]> -SoftwareUpdatePackageName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareUpdateFromPackage [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RefreshDistributionPoint] -SoftwareUpdateName <String[]> -SoftwareUpdatePackage <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
