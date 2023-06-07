Get-CMDeploymentStatusDetails
-----------------------------




### Synopsis
Get the status details of a Configuration Manager deployment.



---


### Description

The Get-CMDeploymentStatusDetails cmdlet gets the status details of a Configuration Manager deployment.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplicationDeploymentStatus](Get-CMApplicationDeploymentStatus)



* [Get-CMBaselineDeploymentStatus](Get-CMBaselineDeploymentStatus)



* [Get-CMPackageDeploymentStatus](Get-CMPackageDeploymentStatus)



* [Get-CMSoftwareUpdateDeploymentStatus](Get-CMSoftwareUpdateDeploymentStatus)





---


### Examples
#### Example 1
```PowerShell
$status = Get-CMPackageDeploymentStatus -Name "TS Name"
Get-CMDeploymentStatusDetails -InputObject $status[1]
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



#### **InputObject**

Specify an deployment status object to get details. Use the Get-CMPackageDeploymentStatus (Get-CMPackageDeploymentStatus.md)cmdlet to get the object. If that cmdlet returns more than one status, it stores them in an array.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|





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
Get-CMDeploymentStatusDetails [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
