Remove-CMSoftwareMeteringRule
-----------------------------




### Synopsis
Removes Configuration Manager software metering rules.



---


### Description

The Remove-CMSoftwareMeteringRule cmdlet removes one or more software metering rules from Configuration Manager.



Software metering monitors and collects software usage data from Configuration Manager clients, such as when clients began using a particular software program and how long users have worked with that software. You can create software metering rules that specify which software to monitor.



You can specify rules to disable by ID or by product name, or use the Get-CMSoftwareMeteringRule (Get-CMSoftwareMeteringRule.md)cmdlet. You can use the Disable-CMSoftwareMeteringRule to temporarily suspend a rule.



For more information about software metering in Configuration Manager, see Introduction to Software Metering in Configuration Manager (/mem/configmgr/apps/deploy-use/monitor-app-usage-with-software-metering).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMSoftwareMeteringRule](Disable-CMSoftwareMeteringRule)



* [Enable-CMSoftwareMeteringRule](Enable-CMSoftwareMeteringRule)



* [Get-CMSoftwareMeteringRule](Get-CMSoftwareMeteringRule)



* [New-CMSoftwareMeteringRule](New-CMSoftwareMeteringRule)



* [Set-CMSoftwareMeteringRule](Set-CMSoftwareMeteringRule)





---


### Examples
#### Example 1: Remove rules for a product
```PowerShell
PS XYZ:\> Remove-CMSoftwareMeteringRule -ProductName "Accounting Package"
Remove
Are you sure you wish to remove SoftwareMeteringRule: RuleID=16777220?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

Remove
Are you sure you wish to remove SoftwareMeteringRule: RuleID=16777221?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```
This command removes any software metering rules for a product named Accounting Package. In this example, there are two rules for that product. The command does not include the Force parameter, so the cmdlet prompts for confirmation for both rules.


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



#### **Id**

Specifies an array of IDs for software metering rules.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |RuleId |



#### **InputObject**

Specifies a software metering rule object. To obtain a software metering rule object, use the Get-CMSoftwareMeteringRule (Get-CMSoftwareMeteringRule.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **ProductName**

Specifies a name for a product that a rule meters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMSoftwareMeteringRule [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareMeteringRule [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMSoftwareMeteringRule [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -ProductName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
