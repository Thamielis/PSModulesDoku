Set-CMDeploymentTypeDependencyGroup
-----------------------------------




### Synopsis
Sets a deployment type dependency group in Configuration Manager.



---


### Description

The Set-CMDeploymentTypeDependencyGroup cmdlet sets a deployment type dependency group in the Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMDeploymentTypeDependencyGroup](New-CMDeploymentTypeDependencyGroup)



* [Get-CMDeploymentTypeDependencyGroup](Get-CMDeploymentTypeDependencyGroup)



* [Remove-CMDeploymentTypeDependencyGroup](Remove-CMDeploymentTypeDependencyGroup)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>  Get-CMDeploymentType -ApplicationName MyApp | Get-CMDeploymentTypeDependencyGroup -GroupName MyGroup | Set-CMDeploymentTypeDependencyGroup -NewName MyNewGroup
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

Specifies a deployment type dependency group.






|Type                             |Required|Position|PipelineInput |Aliases|
|---------------------------------|--------|--------|--------------|-------|
|`[DeploymentTypeDependencyGroup]`|true    |named   |True (ByValue)|Group  |



#### **NewName**

Specifies a new dependency group name.






|Type      |Required|Position|PipelineInput|Aliases                   |
|----------|--------|--------|-------------|--------------------------|
|`[String]`|true    |named   |False        |GroupName<br/>NewGroupName|



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
* IResultObject#SMS_Application






---


### Notes




---


### Syntax
```PowerShell
Set-CMDeploymentTypeDependencyGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <DeploymentTypeDependencyGroup> -NewName <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
