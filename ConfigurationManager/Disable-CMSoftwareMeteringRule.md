Disable-CMSoftwareMeteringRule
------------------------------




### Synopsis
Disables Configuration Manager software metering rules.



---


### Description

The Disable-CMSoftwareMeteringRule cmdlet disables one or more software metering rules in Configuration Manager. If you disable a rule, it does not collect information from clients. You can use the Enable-CMSoftwareMeteringRule (Enable-CMSoftwareMeteringRule.md)cmdlet to enable a rule that you previously disabled.



Software metering monitors and collects software usage data from Configuration Manager clients, such as when clients began using a particular software program and how long users have worked with that software. You can create software metering rules that specify which software to monitor.



You can specify rules that disable software metering rules by ID or by product name, or use the Get-CMSoftwareMeteringRule (Get-CMSoftwareMeteringRule.md)cmdlet. You can use the Remove-CMSoftwareMeteringRule to permanently delete a rule.



For more information about software metering in Configuration Manager, see Introduction to Software Metering in Configuration Manager (/mem/configmgr/apps/deploy-use/monitor-app-usage-with-software-metering).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMSoftwareMeteringRule](Enable-CMSoftwareMeteringRule)



* [Get-CMSoftwareMeteringRule](Get-CMSoftwareMeteringRule)



* [New-CMSoftwareMeteringRule](New-CMSoftwareMeteringRule)



* [Remove-CMSoftwareMeteringRule](Remove-CMSoftwareMeteringRule)



* [Set-CMSoftwareMeteringRule](Set-CMSoftwareMeteringRule)





---


### Examples
#### Example 1: Disable rules for a specific product
```PowerShell
PS XYZ:\>Disable-CMSoftwareMeteringRule -ProductName "Accounting Package"
```
This command disables software metering rules for the product named Accounting Package. There may be more than one rule.
#### Example 2: Disable a specific rule
```PowerShell
PS XYZ:\>Disable-CMSoftwareMeteringRule -Id "16777229"
```
This command disables a software metering rule that has the specified ID.


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
Disable-CMSoftwareMeteringRule [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Disable-CMSoftwareMeteringRule [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Disable-CMSoftwareMeteringRule [-DisableWildcardHandling] [-ForceWildcardHandling] -ProductName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
