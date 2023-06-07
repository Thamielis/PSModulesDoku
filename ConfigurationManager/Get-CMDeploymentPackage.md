Get-CMDeploymentPackage
-----------------------




### Synopsis
Gets information about deployment packages on a distribution point.



---


### Description

The Get-CMDeploymentPackage cmdlet gets information about one or more deployment packages on a distribution point. If you do not specify the DeploymentPackageName parameter, Configuration Manager returns all the deployment packages on the distribution point that you specify.



A deployment package is a Configuration Manager object that contains the content files and instructions for distributing programs, software updates, boot images, operating system images, and drivers to Configuration Manager clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeployment](Get-CMDeployment)



* [Get-CMPackageDeploymentStatus](Get-CMPackageDeploymentStatus)



* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Invoke-CMDeploymentSummarization](Invoke-CMDeploymentSummarization)





---


### Examples
#### Example 1: Get all deployment packages for a distribution point
```PowerShell
PS XYZ:\> Get-CMDeploymentPackage -DistributionPointName "CMCEN-DIST02.TSQA.CORP.CONTOSCO.COM"
```
This command gets all deployment packages that are distributed to clients from the distribution point named CMCEN-DIST02.TSQA.CORP.CONTOSCO.COM.
#### Example 2: Get a deployment package for a distribution point
```PowerShell
PS XYZ:\> Get-CMDeploymentPackage -DistributionPointName "CMCEN-DIST02.TSQA.CORP.CONTOSCO.COM" -DeploymentPackageName "Depack01"
```
This command gets the deployment package named Depack01 that is distributed to clients from the distribution point named CMCEN-DIST02.TSQA.CORP.CONTOSCO.COM.


---


### Parameters
#### **DeploymentPackageName**

Specifies an array of names of deployment packages. If you do not specify this parameter, the cmdlet returns status information about all deployment packages on the distribution point.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Name   |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPointName**

Specifies an array of names of distribution points that are associated with deployment packages.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_DPContentInfo


* IResultObject#SMS_DPContentInfo






---


### Notes




---


### Syntax
```PowerShell
Get-CMDeploymentPackage [-DeploymentPackageName <String>] [-DisableWildcardHandling] -DistributionPointName <String> [-ForceWildcardHandling] [<CommonParameters>]
```
