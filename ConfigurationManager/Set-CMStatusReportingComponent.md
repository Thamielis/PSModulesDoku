Set-CMStatusReportingComponent
------------------------------




### Synopsis
Sets an object representing a status reporting component.



---


### Description

The Set-CMStatusReportingComponent cmdlet sets an object that represents a status reporting component. A status reporting component object specifies information about the client configuration and server configuration components.



You can configure the reporting component to check log files and monitor the severity of entries in the log files.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMStatusReportingComponent](Get-CMStatusReportingComponent)





---


### Examples
#### Example 1: Set status reporting component
```PowerShell
Set-CMStatusReportingComponent -SiteCode "CM1" -ClientReportType AllMilestones -ServerReportType AllMilestones
```



---


### Parameters
#### **ClientLogChecked**

Indicates whether a client log is checked.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClientLogFailureChecked**

Indicates whether a client log failure is checked.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClientLogType**

Specifies a type of client log.



Valid Values:

* AllMilestonesAndAllDetails
* AllMilestones
* ErrorAndWarningMilestones
* ErrorMilestones






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[StatusReportOrLogType]`|false   |named   |False        |



#### **ClientReportChecked**

Indicates whether a client report is checked.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClientReportFailureChecked**

Indicates whether a client failure is checked.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClientReportType**

Specifies a type of report.



Valid Values:

* AllMilestonesAndAllDetails
* AllMilestones
* ErrorAndWarningMilestones
* ErrorMilestones






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[StatusReportOrLogType]`|false   |named   |False        |



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



#### **InputObject**

Specifies an object output from another cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name for a status reporting component in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteName|



#### **ServerLogChecked**

Indicates whether a server log is checked.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ServerLogFailureChecked**

Indicates whether a server log failure is checked.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ServerLogType**

Specifies a server log type.



Valid Values:

* AllMilestonesAndAllDetails
* AllMilestones
* ErrorAndWarningMilestones
* ErrorMilestones






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[StatusReportOrLogType]`|false   |named   |False        |



#### **ServerReportChecked**

Indicates whether a server report is checked.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ServerReportFailureChecked**

Indicates whether a server report failure is checked.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ServerReportType**

Specifies a report type.



Valid Values:

* AllMilestonesAndAllDetails
* AllMilestones
* ErrorAndWarningMilestones
* ErrorMilestones






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[StatusReportOrLogType]`|false   |named   |False        |



#### **SiteCode**

Specifies a site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Set-CMStatusReportingComponent [-ClientLogChecked <Boolean>] [-ClientLogFailureChecked <Boolean>] [-ClientLogType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-ClientReportChecked <Boolean>] [-ClientReportFailureChecked <Boolean>] [-ClientReportType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-ServerLogChecked <Boolean>] [-ServerLogFailureChecked <Boolean>] [-ServerLogType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-ServerReportChecked <Boolean>] [-ServerReportFailureChecked <Boolean>] [-ServerReportType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStatusReportingComponent [-ClientLogChecked <Boolean>] [-ClientLogFailureChecked <Boolean>] [-ClientLogType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-ClientReportChecked <Boolean>] [-ClientReportFailureChecked <Boolean>] [-ClientReportType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-ServerLogChecked <Boolean>] [-ServerLogFailureChecked <Boolean>] [-ServerLogType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-ServerReportChecked <Boolean>] [-ServerReportFailureChecked <Boolean>] [-ServerReportType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMStatusReportingComponent [-ClientLogChecked <Boolean>] [-ClientLogFailureChecked <Boolean>] [-ClientLogType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-ClientReportChecked <Boolean>] [-ClientReportFailureChecked <Boolean>] [-ClientReportType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ServerLogChecked <Boolean>] [-ServerLogFailureChecked <Boolean>] [-ServerLogType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-ServerReportChecked <Boolean>] [-ServerReportFailureChecked <Boolean>] [-ServerReportType {AllMilestonesAndAllDetails | AllMilestones | ErrorAndWarningMilestones | ErrorMilestones}] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
