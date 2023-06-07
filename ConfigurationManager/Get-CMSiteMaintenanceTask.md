Get-CMSiteMaintenanceTask
-------------------------




### Synopsis
Gets maintenance tasks in Configuration Manager.



---


### Description

The Get-CMSiteMaintenanceTask cmdlet gets maintenance tasks in Configuration Manager. A maintenance task is a task in Configuration Manager that performs maintenance on sites and databases.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMSiteMaintenanceTask](Set-CMSiteMaintenanceTask)





---


### Examples
#### Example 1: Get a maintenance task
```PowerShell
Get-CMSiteMaintenanceTask -SiteCode "CM1" -MaintenanceTaskName "Backup SMS Site Server"
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



#### **Name**

{{ Fill Name Description }}






|Type      |Required|Position|PipelineInput|Aliases                                      |
|----------|--------|--------|-------------|---------------------------------------------|
|`[String]`|false   |named   |False        |ItemName<br/>MaintenanceTaskName<br/>TaskName|



#### **SiteCode**

Specifies the site code of the Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_SQLTask


* IResultObject#SMS_SCI_SQLTask






---


### Notes




---


### Syntax
```PowerShell
Get-CMSiteMaintenanceTask [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-SiteCode <String>] [<CommonParameters>]
```
