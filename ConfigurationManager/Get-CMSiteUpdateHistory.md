Get-CMSiteUpdateHistory
-----------------------




### Synopsis
Gets a site update history.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
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



#### **StartDate**








|Type        |Required|Position|PipelineInput|Aliases     |
|------------|--------|--------|-------------|------------|
|`[DateTime]`|false   |named   |False        |DateReleased|





---


### Inputs
None





---


### Outputs
* IResultObject#SMS_CM_UpdatePackagesHistory






---


### Notes




---


### Syntax
```PowerShell
Get-CMSiteUpdateHistory [-DisableWildcardHandling] [-ForceWildcardHandling] [-StartDate <DateTime>] [<CommonParameters>]
```
