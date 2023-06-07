Get-CMPackageDeploymentStatus
-----------------------------




### Synopsis
Get the status of classic software distribution deployments.



---


### Description

The Get-CMPackageDeploymentStatus cmdlet gets the status of one or more classic software distribution deployments. A classic software distribution is a legacy software distribution program on a client.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMPackageDeployment](New-CMPackageDeployment)



* [Get-CMPackageDeployment](Get-CMPackageDeployment)



* [Set-CMPackageDeployment](Set-CMPackageDeployment)



* [Remove-CMPackageDeployment](Remove-CMPackageDeployment)



* [Get-CMPackage](Get-CMPackage)



* [Invoke-CMDeploymentSummarization](Invoke-CMDeploymentSummarization)



* [Remove-CMDeployment](Remove-CMDeployment)





---


### Examples
#### Example 1: Get the status of a deployment
```PowerShell
Get-CMPackageDeploymentStatus -Name "Depack01"
```



---


### Parameters
#### **DeploymentId**

Specifies the ID of a deployment






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



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



#### **InputObject**

Specifies a deployment package.






|Type             |Required|Position|PipelineInput |Aliases                                 |
|-----------------|--------|--------|--------------|----------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Package<br/>Advertisement<br/>Deployment|



#### **Name**

Specifies the name of a package.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |PackageName|



#### **PackageId**

Specifies the ID of a package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **StatusType**

Specifies a status type.



Valid Values:

* Any
* Success
* InProgress
* RequirementsNotMet
* Unknown
* Error






|Type                           |Required|Position|PipelineInput|
|-------------------------------|--------|--------|-------------|
|`[PackageDeploymentStatusType]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes
Cmdlet aliases: Get-CMDeploymentStatus



---


### Syntax
```PowerShell
Get-CMPackageDeploymentStatus -DeploymentId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-StatusType {Any | Success | InProgress | RequirementsNotMet | Unknown | Error}] [<CommonParameters>]
```
```PowerShell
Get-CMPackageDeploymentStatus [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-StatusType {Any | Success | InProgress | RequirementsNotMet | Unknown | Error}] [<CommonParameters>]
```
```PowerShell
Get-CMPackageDeploymentStatus [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-StatusType {Any | Success | InProgress | RequirementsNotMet | Unknown | Error}] [<CommonParameters>]
```
```PowerShell
Get-CMPackageDeploymentStatus [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageId <String> [-StatusType {Any | Success | InProgress | RequirementsNotMet | Unknown | Error}] [<CommonParameters>]
```
