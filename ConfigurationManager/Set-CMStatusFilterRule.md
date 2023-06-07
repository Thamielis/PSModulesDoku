Set-CMStatusFilterRule
----------------------




### Synopsis
Modifies settings for a Configuration Manager filter rule for status messages.



---


### Description

The Set-CMStatusFilterRule cmdlet modifies settings for a Configuration Manager filter rule for status messages. Configuration Manager checks a status message against rules in order of priority. A rule can specify that rules with lower priority do not apply to a message after that rule applied.



Status filter rules specify how Configuration Manager responds to status messages. Each filter rule contains criteria and actions for status messages. You configure status filter rules for each site, not across all sites.



To change the priority of a rule, use the rule name to specify the rule.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMStatusFilterRule](Disable-CMStatusFilterRule)



* [Enable-CMStatusFilterRule](Enable-CMStatusFilterRule)



* [Get-CMStatusFilterRule](Get-CMStatusFilterRule)



* [New-CMStatusFilterRule](New-CMStatusFilterRule)



* [Remove-CMStatusFilterRule](Remove-CMStatusFilterRule)





---


### Examples
#### Example 1: Increase the priority of a rule
```PowerShell
PS XYZ:\> Set-CMStatusFilterRule -Name "Status change to critical" -SiteCode "CM1" -Priority Increase
```
This command increases the priority of a filter rule that has the specified name in a site that has the site code CM1.


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


Valid values are:


* Audit


* Detail


* Milestone


* None



Valid Values:

* None
* Milestone
* Detail
* Audit






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[MessageType]`|false   |named   |False        |



#### **Name**

Specifies an array of names for status filter rules.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Priority**

Specifies a change in priority. Configuration Manager checks status messages against rules in order of rule priority. Valid values are: Decrease and Increase.



Valid Values:

* Increase
* Decrease






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PriorityChangeType]`|false   |named   |False        |



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

Specifies a replication priority for sending status messages to the parent site.


Valid values are:


* High


* Low


* Medium



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


Valid values are:


* Error


* Informational


* None


* Warning



Valid Values:

* None
* Informational
* Warning
* Error






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SeverityType]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of a site system server in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Source**

Specifies the status message source to match. The possible sources are the following:


* Client


* SMS Provider


* Site Server






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StatusFilterRuleSiteCode**

Specifies a site code for the site from which the status message originated.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **WriteToDatabase**

Indicates whether to write a message to the database. Specify a value of $True for this parameter to enable the AllowUserDeleteMessagesAfterThresholdDays parameter.






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
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMStatusFilterRule [-AllowDeleteAfterDays <Int32>] [-ComponentName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ForwardToStatusSummarizer <Boolean>] [-MessageId <Int32>] [-MessageType {None | Milestone | Detail | Audit}] -Name <String> [-Priority {Increase | Decrease}] [-ProcessLowerPriorityRule <Boolean>] [-ProgramPath <String>] [-PropertyId <String>] [-PropertyValue <String>] [-ReplicateToParentSite <Boolean>] [-ReplicationPriority {High | Medium | Low}] [-ReportToEventLog <Boolean>] [-RunProgram <Boolean>] [-SeverityType {None | Informational | Warning | Error}] [-SiteCode <String>] [-SiteSystemServerName <String>] [-Source <String>] [-StatusFilterRuleSiteCode <String>] [-WriteToDatabase <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
