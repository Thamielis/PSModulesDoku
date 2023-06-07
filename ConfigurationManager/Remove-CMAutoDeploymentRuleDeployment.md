Remove-CMAutoDeploymentRuleDeployment
-------------------------------------




### Synopsis
Removes a deployment from an auto deployment rule.



---


### Description

The Remove-CMAutoDeploymentRuleDeployment cmdlet removes a deployment from an auto deployment rule.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAutoDeploymentRuleDeployment](Get-CMAutoDeploymentRuleDeployment)



* [New-CMAutoDeploymentRuleDeployment](New-CMAutoDeploymentRuleDeployment)



* [Set-CMAutoDeploymentRuleDeployment](Set-CMAutoDeploymentRuleDeployment)





---


### Examples
#### Example 1: Remove a deployment
```PowerShell
PS XYZ:\> $Deployments = Get-CMAutoDeploymentRuleDeployment -Name "TestRule01"
PS XYZ:\> Remove-CMAutoDeploymentRuleDeployment -InputObject $Deployments[0]
```
The first command gets the deployment objects associated with the automatic deployment rule named TestRule01 and stores the objects in the $Deployments variable.


The second command removes the first deployment object stored in $Deployments.


---


### Parameters
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

Specifies an automatic deployment rule deployment object. To obtain a deployment object, use the Get-CMAutoDeploymentRuleDeployment (Get-CMAutoDeploymentRuleDeployment.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                     |
|-----------------|--------|--------|--------------|----------------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|AutoDeploymentRuleDeployment|



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
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMAutoDeploymentRuleDeployment [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
