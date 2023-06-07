Remove-CMDeploymentTypeDependency
---------------------------------




### Synopsis
Removes a deployment type dependency from Configuration Manager deployment type dependency group.



---


### Description

The Remove-CMDeploymentTypeDependency cmdlet removes a deployment type dependency from a deployment type dependency group. If removing a dependency causes the group to have no more dependencies, the group will be removed. Required input is a deployment type object from Get-CMDeploymentType (./Get-CMDeploymentType.md) or [Get-CMDeploymentTypeDependency](./Get-CMDeploymentTypeDependency.md) and a dependency group from [Get-CMDeploymentTypeDependencyGroup](./Get-CMDeploymentTypeDependencyGroup.md).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeploymentTypeDependency](Add-CMDeploymentTypeDependency)



* [Get-CMDeploymentTypeDependency](Get-CMDeploymentTypeDependency)



* [Set-CMDeploymentTypeDependency](Set-CMDeploymentTypeDependency)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $dpGroup = Get-CMDeploymentType -ApplicationName MyApp | Get-CMDeploymentTypeDependencyGroup -GroupName MyGroup
PS XYZ:\> $dpDeps = Get-CMDeploymentTypeDependency -Group $dpGroup
PS XYZ:\> Remove-CMDeploymentTypeDependency -Group $dpGroup -DeploymentTypeDependency $dpDeps[1] -Force
```
This command removes a deployment type dependency.


---


### Parameters
#### **DeploymentTypeDependency**

Specifies a deployment type object.






|Type               |Required|Position|PipelineInput|Aliases                   |
|-------------------|--------|--------|-------------|--------------------------|
|`[IResultObject[]]`|true    |named   |False        |DeploymentTypeDependencies|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






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
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.AppMan.DeploymentTypeDependencyGroup





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMDeploymentTypeDependency -DeploymentTypeDependency <IResultObject[]> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <DeploymentTypeDependencyGroup> [-Confirm] [-WhatIf] [<CommonParameters>]
```
