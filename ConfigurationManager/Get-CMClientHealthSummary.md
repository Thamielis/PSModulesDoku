Get-CMClientHealthSummary
-------------------------




### Synopsis
Gets a client health summary.



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
#### **CollectionId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EndDate**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **StartDate**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_CH_SummaryCurrent


* IResultObject#SMS_CH_SummaryHistory






---


### Notes




---


### Syntax
```PowerShell
Get-CMClientHealthSummary -CollectionId <String> [-DisableWildcardHandling] [-EndDate <DateTime>] [-ForceWildcardHandling] [-StartDate <DateTime>] [<CommonParameters>]
```
```PowerShell
Get-CMClientHealthSummary -CollectionName <String> [-DisableWildcardHandling] [-EndDate <DateTime>] [-ForceWildcardHandling] [-StartDate <DateTime>] [<CommonParameters>]
```
```PowerShell
Get-CMClientHealthSummary [-DisableWildcardHandling] [-EndDate <DateTime>] [-ForceWildcardHandling] -InputObject <IResultObject> [-StartDate <DateTime>] [<CommonParameters>]
```
