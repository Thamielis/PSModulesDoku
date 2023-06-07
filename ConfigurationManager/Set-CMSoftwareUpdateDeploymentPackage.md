Set-CMSoftwareUpdateDeploymentPackage
-------------------------------------




### Synopsis
Modify a software update deployment package.



---


### Description

Use this cmdlet to modify a software update deployment package. A software update deployment package contains one or more software updates for deployment to a collection of computers. For more information, see Deploy software updates (/mem/configmgr/sum/deploy-use/download-software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateDeploymentPackage](Get-CMSoftwareUpdateDeploymentPackage)



* [New-CMSoftwareUpdateDeploymentPackage](New-CMSoftwareUpdateDeploymentPackage)



* [Remove-CMSoftwareUpdateDeploymentPackage](Remove-CMSoftwareUpdateDeploymentPackage)



* [Save-CMSoftwareUpdate](Save-CMSoftwareUpdate)



* [Deploy software updates](Deploy software updates)



* [Software updates maintenance](Software updates maintenance)





---


### Examples
#### Example 1: Update the name and description of a deployment package
```PowerShell
Set-CMSoftwareUpdateDeploymentPackage -Id "ST10000C" -Description "Deployment pack 107" -NewName "SDPTest"
```



---


### Parameters
#### **Description**

Specify an optional description for the deployment package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Add this parameter to force remove an expired NAP update.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of a deployment package to modify.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **InputObject**

Specify a deployment package object to modify. To get this object, use the Get-CMSoftwareUpdateDeploymentPackage (Get-CMSoftwareUpdateDeploymentPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of the deployment package to modify.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Specify a new name for the deployment package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

Specify a package source path for the deployment package.






|Type      |Required|Position|PipelineInput|Aliases                            |
|----------|--------|--------|-------------|-----------------------------------|
|`[String]`|false   |named   |False        |PackageSourcePath<br/>PkgSourcePath|



#### **Priority**

Specify the order in which the site sends the content to other sites and the distribution points in this site.


The site sends high priority content before packages with medium or low priority. Packages with equal priority are sent in the order in which they're created.



Valid Values:

* High
* Normal
* Low






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[Priorities]`|false   |named   |False        |



#### **RefreshDistributionPoint**

Add this parameter to refresh the package on distribution points.






|Type      |Required|Position|PipelineInput|Aliases                                                     |
|----------|--------|--------|-------------|------------------------------------------------------------|
|`[Switch]`|false   |named   |False        |RefreshDistributionPointAfterRemoveSoftwareUpdateFromPackage|



#### **RemoveExpired**

Add this parameter to decline updates that aren't approved and have been expired by Microsoft.






|Type      |Required|Position|PipelineInput|Aliases                                         |
|----------|--------|--------|-------------|------------------------------------------------|
|`[Switch]`|false   |named   |False        |RemoveDownloadedExpiredSoftwareUpdateFromPackage|



#### **RemoveSuperseded**

Add this parameter to decline updates that haven't been approved for 30 days or more, aren't currently needed by any clients, and are superseded by an approved update.






|Type      |Required|Position|PipelineInput|Aliases                                            |
|----------|--------|--------|-------------|---------------------------------------------------|
|`[Switch]`|false   |named   |False        |RemoveDownloadedSupersededSoftwareUpdateFromPackage|



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
Set-CMSoftwareUpdateDeploymentPackage [-Description <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-PassThru] [-Path <String>] [-Priority {High | Normal | Low}] [-RefreshDistributionPoint] [-RemoveExpired] [-RemoveSuperseded] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdateDeploymentPackage [-Description <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-Path <String>] [-Priority {High | Normal | Low}] [-RefreshDistributionPoint] [-RemoveExpired] [-RemoveSuperseded] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdateDeploymentPackage [-Description <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-Path <String>] [-Priority {High | Normal | Low}] [-RefreshDistributionPoint] [-RemoveExpired] [-RemoveSuperseded] [-Confirm] [-WhatIf] [<CommonParameters>]
```
