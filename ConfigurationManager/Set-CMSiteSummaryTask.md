Set-CMSiteSummaryTask
---------------------




### Synopsis
Sets a site summary task.



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
#### **DisableFixedRun**








|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[Switch]`|false   |named   |False        |DisableFixedRunInterval|



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
|`[Int32]`|true    |named   |False        |SummaryTaskId|



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases          |
|-----------------|--------|--------|--------------|-----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SummaryTaskObject|



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RunIntervalMins**








|Type     |Required|Position|PipelineInput|Aliases           |
|---------|--------|--------|-------------|------------------|
|`[Int32]`|false   |named   |False        |RunIntervalMinutes|



#### **RunNow**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteCode**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskName**








|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|true    |named   |False        |SummaryTaskName|



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
Set-CMSiteSummaryTask [-DisableFixedRun] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-PassThru] [-RunIntervalMins <Int32>] [-RunNow] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSiteSummaryTask [-DisableFixedRun] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-RunIntervalMins <Int32>] [-RunNow] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSiteSummaryTask [-DisableFixedRun] [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-RunIntervalMins <Int32>] [-RunNow] [-SiteCode <String>] -TaskName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
