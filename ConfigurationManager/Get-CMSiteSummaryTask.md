Get-CMSiteSummaryTask
---------------------




### Synopsis
Gets a site summary task.



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



#### **Id**








|Type     |Required|Position|PipelineInput|Aliases      |
|---------|--------|--------|-------------|-------------|
|`[Int32]`|false   |0       |False        |SummaryTaskId|



#### **TaskName**








|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |0       |False        |SummaryTaskName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SummaryTask


* IResultObject#SMS_SummaryTask






---


### Notes




---


### Syntax
```PowerShell
Get-CMSiteSummaryTask [[-Id] <Int32>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMSiteSummaryTask [[-TaskName] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
