Set-CMStatusSummarizer
----------------------




### Synopsis
Modifies settings of a Configuration Manager status summarizer.



---


### Description

The Set-CMStatusSummarizer cmdlet modifies settings of a status summarizer. The Configuration Manager status summarizers apply to the areas of application deployment, application statistics, component status, and site system status.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMSchedule](New-CMSchedule)



* [Get-CMStatusSummarizer](Get-CMStatusSummarizer)





---


### Examples
#### Example 1: Modify a status summarizer
```PowerShell
PS XYZ:\> Set-CMStatusSummarizer -ApplicationDeploymentSummarizer -SiteCode "ContosoSite"
```
This command configures the status summarizer for the Contoso site to return application deployment statistics.


---


### Parameters
#### **ApplicationDeploymentSummarizer**

Indicates that the summarizer is an application deployment status summarizer.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ApplicationStatisticSummarizer**

Indicates that the summarizer is an application statistic status summarizer.






|Type      |Required|Position|PipelineInput|Aliases                        |
|----------|--------|--------|-------------|-------------------------------|
|`[Switch]`|true    |named   |False        |ApplicationStatisticsSummarizer|



#### **ComponentStatusSummarizer**

Indicates that the summarizer is a component status summarizer.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **CriticalSizeKB**

Specifies the threshold, in kilobytes, of free space for a Critical message. This parameter applies to site system status summarizers.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Days**








|Type     |Required|Position|PipelineInput|Aliases    |
|---------|--------|--------|-------------|-----------|
|`[Int32]`|false   |named   |False        |DayInterval|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableStatusSummarizer**

Indicates whether to enable Configuration Manager to summarize status messages for the site. This parameter applies to component status summarizers and site system status summarizers.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Hours**








|Type     |Required|Position|PipelineInput|Aliases     |
|---------|--------|--------|-------------|------------|
|`[Int32]`|false   |named   |False        |HourInterval|



#### **Minutes**








|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|false   |named   |False        |MinuteInterval|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ReplicateToParentSite**

Indicates whether to pass summarization data from this site to its parent site. This parameter applies to component status summarizers and site system status summarizers. If you specify a value of $True for this parameter, specify a priority by using the ReplicationPriority parameter and a threshold period by using the ThresholdPeriod parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ReplicationPriority**

Specifies the priority of replication to the parent site. The acceptable values for this parameter are: Low, Normal, and High. Specify this parameter if you specify $True for the ReplicateToParentSite parameter.



Valid Values:

* Low
* Normal
* High






|Type                       |Required|Position|PipelineInput|
|---------------------------|--------|--------|-------------|
|`[ReplicationPriorityType]`|false   |named   |False        |



#### **Schedule**

Specifies a schedule object that determines how often to summarize site system status. To obtain a schedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemStatusSummarizer**

Indicates that the summarizer is a site system status summarizer.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **TimeThreshold**





Valid Values:

* Since 0:00:00
* Since 4:00:00
* Since 8:00:00
* Since 12:00:00
* Since 16:00:00
* Since 20:00:00
* Since Sunday
* Since Monday
* Since Tuesday
* Since Wednesday
* Since Thursday
* Since Friday
* Since Saturday
* Since 15th of the Month
* Since 1st of the Month
* Since Site Installation






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |named   |False        |ThresholdPeriod|



#### **WarningSizeKB**

Specifies the threshold, in kilobytes, of free space for a Warning message. This parameter applies to site system status summarizers.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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
None





---


### Outputs
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMStatusSummarizer -ApplicationDeploymentSummarizer [-Days <Int32>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Hours <Int32>] [-Minutes <Int32>] [-PassThru] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStatusSummarizer -ApplicationStatisticSummarizer [-Days <Int32>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Hours <Int32>] [-Minutes <Int32>] [-PassThru] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStatusSummarizer -ComponentStatusSummarizer [-DisableWildcardHandling] [-EnableStatusSummarizer <Boolean>] [-ForceWildcardHandling] [-PassThru] [-ReplicateToParentSite <Boolean>] [-ReplicationPriority {Low | Normal | High}] [-SiteCode <String>] [-TimeThreshold {Since 0:00:00 | Since 4:00:00 | Since 8:00:00 | Since 12:00:00 | Since 16:00:00 | Since 20:00:00 | Since Sunday | Since Monday | Since Tuesday | Since Wednesday | Since Thursday | Since Friday | Since Saturday | Since 15th of the Month | Since 1st of the Month | Since Site Installation}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStatusSummarizer [-CriticalSizeKB <Int32>] [-DisableWildcardHandling] [-EnableStatusSummarizer <Boolean>] [-ForceWildcardHandling] [-PassThru] [-ReplicateToParentSite <Boolean>] [-ReplicationPriority {Low | Normal | High}] [-Schedule <IResultObject>] [-SiteCode <String>] -SiteSystemStatusSummarizer [-WarningSizeKB <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
