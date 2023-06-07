Enable-CMStatusFilterRule
-------------------------




### Synopsis
Enables a Configuration Manager filter rule for status messages.



---


### Description

The Enable-CMStatusFilterRule cmdlet enables a specified Configuration Manager filter rule for status messages.



Status filter rules specify how Configuration Manager responds to status messages. Each filter rule contains criteria and actions for status messages. You configure status filter rules for each site, not across all sites.



Use the rule name and site code to specify a rule to enable. You can use the Disable-CMStatusFilterRule (Disable-CMStatusFilterRule.md)cmdlet to disable a rule. To remove a rule permanently, use the Remove-CMStatusFilterRule (Remove-CMStatusFilterRule.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMStatusFilterRule](Disable-CMStatusFilterRule)



* [Get-CMStatusFilterRule](Get-CMStatusFilterRule)



* [New-CMStatusFilterRule](New-CMStatusFilterRule)



* [Remove-CMStatusFilterRule](Remove-CMStatusFilterRule)



* [Set-CMStatusFilterRule](Set-CMStatusFilterRule)





---


### Examples
#### Example 1: Enable a status filter rule
```PowerShell
PS XYZ:\>Enable-CMStatusFilterRule -Name "Status change to critical" -SiteCode "CM1"
```
This command enables a status filter rule that has the specified name in a site that has the site code CM1.


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

Specifies a status filter rule object to enable. To obtain a status filter rule object, use the Get-CMStatusFilterRule (Get-CMStatusFilterRule.md)cmdlet.






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
Enable-CMStatusFilterRule [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Enable-CMStatusFilterRule [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
