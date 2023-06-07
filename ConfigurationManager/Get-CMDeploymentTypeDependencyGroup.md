Get-CMDeploymentTypeDependencyGroup
-----------------------------------




### Synopsis
Gets a deployment type dependency group from Configuration Manager.



---


### Description

The Get-CMDeploymentTypeDependencyGroup cmdlet gets a deployment type dependency group from the Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDeploymentTypeDependencyGroup](New-CMDeploymentTypeDependencyGroup)



* [Set-CMDeploymentTypeDependencyGroup](Set-CMDeploymentTypeDependencyGroup)



* [Remove-CMDeploymentTypeDependencyGroup](Remove-CMDeploymentTypeDependencyGroup)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>  Get-CMDeploymentType -ApplicationName MyApp | Get-CMDeploymentTypeDependencyGroup
```
This command returns the dependency groups of a deployment type.


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



#### **GroupId**

{{ Fill GroupId Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **GroupName**

Specifies a dependency group name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InputObject**

Specifies a deployment type object.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* DeploymentTypeDependencyGroup[]


* DeploymentTypeDependency






---


### Notes




---


### Syntax
```PowerShell
Get-CMDeploymentTypeDependencyGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-GroupId <String>] [-GroupName <String>] -InputObject <IResultObject> [<CommonParameters>]
```
