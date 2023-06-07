New-CMDeploymentTypeDependencyGroup
-----------------------------------




### Synopsis
Creates a deployment type dependency group in Configuration Manager.



---


### Description

The New-CMDeploymentTypeDependencyGroup cmdlet creates a deployment type dependency group in the Configuration Manager. Must be added to an existing deployment type by using Add-CMDeploymentTypeDependency (./Add-CMDeploymentTypeDependency.md).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeploymentTypeDependencyGroup](Get-CMDeploymentTypeDependencyGroup)



* [Set-CMDeploymentTypeDependencyGroup](Set-CMDeploymentTypeDependencyGroup)



* [Remove-CMDeploymentTypeDependencyGroup](Remove-CMDeploymentTypeDependencyGroup)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>  Get-CMDeploymentType -ApplicationName MyApp | New-CMDeploymentTypeDependencyGroup -GroupName MyGroup
```
This command creates a new dependency group call MyGroup for the deployment type MyApp.


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



#### **GroupName**

Specifies a group name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **InputObject**

Specifies a deployment type object.






|Type             |Required|Position|PipelineInput |Aliases                                         |
|-----------------|--------|--------|--------------|------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ParentDeploymentType<br/>DependingDeploymentType|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.AppMan.DeploymentTypeDependencyGroup






---


### Notes




---


### Syntax
```PowerShell
New-CMDeploymentTypeDependencyGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -GroupName <String> -InputObject <IResultObject> [<CommonParameters>]
```
