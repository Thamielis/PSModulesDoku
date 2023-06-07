Get-CMDefaultBoundaryGroup
--------------------------




### Synopsis
Gets a default boundary group.



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



#### **GroupId**








|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteCode**








|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|true    |named   |False        |DefaultSiteCode|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_DefaultBoundaryGroup


* IResultObject#SMS_DefaultBoundaryGroup






---


### Notes




---


### Syntax
```PowerShell
Get-CMDefaultBoundaryGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -GroupId <Int32> [<CommonParameters>]
```
```PowerShell
Get-CMDefaultBoundaryGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDefaultBoundaryGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -SiteCode <String> [<CommonParameters>]
```
