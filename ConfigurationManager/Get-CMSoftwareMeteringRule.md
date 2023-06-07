Get-CMSoftwareMeteringRule
--------------------------




### Synopsis
Gets Configuration Manager software metering rules.



---


### Description

The Get-CMSoftwareMeteringRule cmdlet gets one or more software metering rules in Configuration Manager. You can use this cmdlet to get rules to pass to other cmdlets, such as the Enable-CMSoftwareMeteringRule (Enable-CMSoftwareMeteringRule.md) cmdlet or the [Remove-CMSoftwareMeteringRule](Remove-CMSoftwareMeteringRule.md)cmdlet.



Software metering monitors and collects software usage data from Configuration Manager clients, such as when clients began using a particular software program and how long users have worked with that software. You can create software metering rules that specify which software to monitor.



You can specify rules by ID or by product name.



For more information about software metering in Configuration Manager, see Introduction to Software Metering in Configuration Manager (/mem/configmgr/apps/deploy-use/monitor-app-usage-with-software-metering).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMSoftwareMeteringRule](Disable-CMSoftwareMeteringRule)



* [Enable-CMSoftwareMeteringRule](Enable-CMSoftwareMeteringRule)



* [New-CMSoftwareMeteringRule](New-CMSoftwareMeteringRule)



* [Remove-CMSoftwareMeteringRule](Remove-CMSoftwareMeteringRule)



* [Set-CMSoftwareMeteringRule](Set-CMSoftwareMeteringRule)





---


### Examples
#### Example 1: Get rules for a product
```PowerShell
PS XYZ:\> Get-CMSoftwareMeteringRule -ProductName "Accounting Package"
```
This command gets software metering rules for the product named Accounting Package.


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



#### **ProductName**

Specifies a name for a product that a rule meters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_MeteredProductRule


* IResultObject#SMS_MeteredProductRule






---


### Notes




---


### Syntax
```PowerShell
Get-CMSoftwareMeteringRule [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareMeteringRule [-DisableWildcardHandling] [-ForceWildcardHandling] [-ProductName <String>] [<CommonParameters>]
```
