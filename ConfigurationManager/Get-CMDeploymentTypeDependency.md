Get-CMDeploymentTypeDependency
------------------------------




### Synopsis
Gets a deployment type from a dependency group.



---


### Description

The Get-CMDeploymentTypeDependency cmdlet gets existing dependent deployment types from a dependency group. Required input is a dependency group object from Get-CMDeploymentTypeDependencyGroup (./Get-CMDeploymentTypeDependencyGroup.md).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeploymentTypeDependency](Add-CMDeploymentTypeDependency)



* [Set-CMDeploymentTypeDependency](Set-CMDeploymentTypeDependency)



* [Remove-CMDeploymentTypeDependency](Remove-CMDeploymentTypeDependency)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> Get-CMDeploymentType -ApplicationName MyApp | Get-CMDeploymentTypeDependencyGroup -GroupName MyGroup | Get-CMDeploymentTypeDependency
```
This command gets a deployment type from a dependency group.


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

Specifies a deployment type dependency group object.






|Type                             |Required|Position|PipelineInput |Aliases|
|---------------------------------|--------|--------|--------------|-------|
|`[DeploymentTypeDependencyGroup]`|true    |named   |True (ByValue)|Group  |





---


### Inputs
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.AppMan.DeploymentTypeDependencyGroup





---


### Outputs
* IResultObject[]#SMS_DeploymentType


* IResultObject#SMS_DeploymentType






---


### Notes




---


### Syntax
```PowerShell
Get-CMDeploymentTypeDependency [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <DeploymentTypeDependencyGroup> [<CommonParameters>]
```
