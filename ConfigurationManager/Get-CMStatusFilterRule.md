Get-CMStatusFilterRule
----------------------




### Synopsis
Gets Configuration Manager filter rules for status messages.



---


### Description

The Get-CMStatusFilterRule cmdlet gets filter rules for Configuration Manager status messages. You can get all the rules for a Configuration Manager site or you can specify a name of a rule within a site.



Status filter rules specify how Configuration Manager responds to status messages. Each filter rule contains criteria and actions for status messages. You configure status filter rules for each site, not across all sites.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMStatusFilterRule](Disable-CMStatusFilterRule)



* [Enable-CMStatusFilterRule](Enable-CMStatusFilterRule)



* [New-CMStatusFilterRule](New-CMStatusFilterRule)



* [Remove-CMStatusFilterRule](Remove-CMStatusFilterRule)



* [Set-CMStatusFilterRule](Set-CMStatusFilterRule)





---


### Examples
#### Example 1: Get rules for a specified site
```PowerShell
PS XYZ:\> Get-CMStatusFilterRule -SiteCode "CM1"
```
This cmdlet gets status filter rules for the site that has the site code CM1.


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



#### **Name**

Specifies a name of a rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteCode**

Specifies a site code for the Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_SCPropertyList


* IResultObject#SMS_SCI_SCPropertyList






---


### Notes




---


### Syntax
```PowerShell
Get-CMStatusFilterRule [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-SiteCode <String>] [<CommonParameters>]
```
