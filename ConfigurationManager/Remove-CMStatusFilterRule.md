Remove-CMStatusFilterRule
-------------------------




### Synopsis
Removes a specified Configuration Manager filter rule for status messages.



---


### Description

The Remove-CMStatusFilterRule cmdlet removes a specified Configuration Manager filter rule for status messages.



Status filter rules specify how Configuration Manager responds to status messages. Each filter rule contains criteria and actions for status messages. You configure status filter rules for each site, not across all sites.



Use the rule name and site code to specify a rule to remove. This cmdlet deletes rules permanently. You can use the Disable-CMStatusFilterRule (Disable-CMStatusFilterRule.md)cmdlet to suspend a rule.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMStatusFilterRule](Disable-CMStatusFilterRule)



* [Enable-CMStatusFilterRule](Enable-CMStatusFilterRule)



* [Get-CMStatusFilterRule](Get-CMStatusFilterRule)



* [New-CMStatusFilterRule](New-CMStatusFilterRule)



* [Set-CMStatusFilterRule](Set-CMStatusFilterRule)





---


### Examples
#### Example 1: Remove a rule
```PowerShell
PS XYZ:\> Remove-CMStatusFilterRule -Name "Status change to critical" -SiteCode "CM1" -Force
```
This command removes a status filter rule that has the specified name in a site that has the site code CM1. The command includes the Force parameter, so the cmdlet does not prompt you for confirmation.


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

Specifies a status filter rule object to remove. To obtain a status filter rule object, use the Get-CMStatusFilterRule (Get-CMStatusFilterRule.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name of a rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SiteCode**

Specifies a site code for the Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Remove-CMStatusFilterRule [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMStatusFilterRule [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
