Add-CMDeploymentTypeDependency
------------------------------




### Synopsis
Adds a deployment type as a dependency to a dependency group in Configuration Manager.



---


### Description

The Add-CMDeploymentTypeDependency adds a deployment type as a dependency to a dependency group. Required input is a deployment type object from Get-CMDeploymentType (./Get-CMDeploymentType.md) and a dependency group from [Get-CMDeploymentTypeDependencyGroup](./Get-CMDeploymentTypeDependencyGroup.md) and [New-CMDeploymentTypeDependencyGroup](./New-CMDeploymentTypeDependencyGroup.md).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeploymentTypeDependency](Get-CMDeploymentTypeDependency)



* [Set-CMDeploymentTypeDependency](Set-CMDeploymentTypeDependency)



* [Remove-CMDeploymentTypeDependency](Remove-CMDeploymentTypeDependency)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>  Get-CMDeploymentType -ApplicationName MyApp | New-CMDeploymentTypeDependencyGroup -GroupName MyGroup | Add-CMDeploymentTypeDependency -DeploymentTypeDependency (Get-CMDeploymentType -ApplicationName MyChildApp) -IsAutoInstall $true
```
This command adds a deployment type dependency.


---


### Parameters
#### **DeploymentTypeDependency**

Specifies a deployment type object.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|true    |named   |False        |



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



#### **IsAutoInstall**

Indicate whether install automatically.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
Add-CMDeploymentTypeDependency -DeploymentTypeDependency <IResultObject[]> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <DeploymentTypeDependencyGroup> [-IsAutoInstall <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
