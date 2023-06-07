New-CMStatusFilterRule
----------------------




### Synopsis
Creates a rule in Configuration Manager.



---


### Description

The New-CMStatusFilterRule cmdlet creates a rule that triggers one or more actions that alerts an administrator to a specific message in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMStatusFilterRule](Disable-CMStatusFilterRule)



* [Enable-CMStatusFilterRule](Enable-CMStatusFilterRule)



* [Get-CMStatusFilterRule](Get-CMStatusFilterRule)



* [Remove-CMStatusFilterRule](Remove-CMStatusFilterRule)



* [Set-CMStatusFilterRule](Set-CMStatusFilterRule)





---


### Examples
#### Example 1: Create a status filter rule
```PowerShell
New-CMStatusFilterRule -SiteCode "XYZ" -Name "Detect when the component status summarizer resets the status of a component." -Source "Site Server" -ComponentName "SMS_COMPONENT_STATUS_SUMMARIZER" -MessageId "4611" -ReportToEventLog $True -ReplicateToParentSite $False -RunProgram $False -ForwardToStatusSummarizer $True -ProcessLowerPriorityRule $True
```



---


### Parameters
#### **AllowDeleteAfterDays**








|Type     |Required|Position|PipelineInput|Aliases                                  |
|---------|--------|--------|-------------|-----------------------------------------|
|`[Int32]`|false   |named   |False        |AllowUserDeleteMessagesAfterThresholdDays|



#### **ComponentName**

Specifies the Configuration Manager component that corresponds to the status messages.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **ForwardToStatusSummarizer**

Indicates whether to forward to the status summarizer.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MessageId**

Specifies a message ID in Configuration Manager.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MessageType**

Specifies a status message type in Configuration Manager.



Valid Values:

* None
* Milestone
* Detail
* Audit






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[MessageType]`|false   |named   |False        |



#### **Name**

Specifies a name for the status filter rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ProcessLowerPriorityRule**

Indicates whether to process a lower priority rule, which prevents further rule processing.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ProgramPath**

Specifies a path to a program that runs when a status message matches the status filter rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PropertyId**

Specifies a property ID in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PropertyValue**

Specifies a value for the corresponding PropertyId parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ReplicateToParentSite**

Indicates whether to pass a message to the parent site.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ReplicationPriority**

Specifies a replication priority for sending status messages to the parent site. The acceptable values for this parameter are: High, Low, and Medium.



Valid Values:

* Low
* Medium
* High






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ReplicationPriority]`|false   |named   |False        |



#### **ReportToEventLog**

Indicates whether to report an event in the Windows event log.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RunProgram**

Indicates whether to run a program when a status message matches a filter rule.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SeverityType**

Specifies the severity of a status message.



Valid Values:

* None
* Informational
* Warning
* Error






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SeverityType]`|false   |named   |False        |



#### **SiteCode**

Specifies a Configuration Manager site code that defines the status rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies a name of the site system server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Source**

Specifies the status message source to match.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StatusFilterRuleSiteCode**

Specifies a site code for the status filter rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **WriteToDatabase**

Indicates whether to write a message to the database. Must be set to enable the AllowUserDeleteMessagesAfterThresholdDays parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* IResultObject#SMS_SCI_SCPropertyList






---


### Notes




---


### Syntax
```PowerShell
New-CMStatusFilterRule [-AllowDeleteAfterDays <Int32>] [-ComponentName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ForwardToStatusSummarizer <Boolean>] [-MessageId <Int32>] [-MessageType {None | Milestone | Detail | Audit}] -Name <String> [-ProcessLowerPriorityRule <Boolean>] [-ProgramPath <String>] [-PropertyId <String>] [-PropertyValue <String>] [-ReplicateToParentSite <Boolean>] [-ReplicationPriority {Low | Medium | High}] [-ReportToEventLog <Boolean>] [-RunProgram <Boolean>] [-SeverityType {None | Informational | Warning | Error}] [-SiteCode <String>] [-SiteSystemServerName <String>] [-Source <String>] [-StatusFilterRuleSiteCode <String>] [-WriteToDatabase <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
