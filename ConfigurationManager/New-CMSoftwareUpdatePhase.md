New-CMSoftwareUpdatePhase
-------------------------




### Synopsis
Use this cmdlet to create a deployment phase for software update.



---


### Description

Use this cmdlet to create a deployment phase for software update.



---


### Examples
#### Example 1: Create a software update phase
```PowerShell
New-CMSoftwareUpdatePhase `
 -CollectionName "MyCollection" `
 -PhaseName "MySUPhase" `
 -UserNotificationOption DisplaySoftwareCenterOnly
```



---


### Parameters
#### **AlertDelta**

This parameter is the same as the following setting on the Alerts page of the Add Phase Wizard in the console: Offset from the deadline time . Specify an integer value for the offset, and then specify the period type with the AlertUnit parameter.


To set this value, you have to use the EnableAlert parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **AlertThresholdPercentage**

This parameter is the same as the following setting on the Alerts page of the Add Phase Wizard in the console: Client compliance is below the following (percent) . Specify an integer value for the percentage. To set this value, you have to use the EnableAlert parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **AlertUnit**

Specify the type of period. Use this parameter with AlertDelta .



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **AllowMeteredConnection**

This parameter is the same as the following setting on the Download Settings page of the Add Phase Wizard in the console: Allow clients on a metered internet connection to download content after the installation deadline, which might incur additional costs .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowSystemRestart**

This parameter is the same as the following setting on the User Experience page of the Add Phase Wizard in the console: System restart (if required to complete installation) . This setting applies when the installation deadline is reached, to allow this activity to be performed outside the maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowWumuFallback**

This parameter is the same as the following setting on the Download Settings page of the Add Phase Wizard in the console: If software updates are not available on distribution point in current, neighbor or site boundary groups, download content from Microsoft Updates .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **BeginCondition**

Specify an option for beginning this phase of deployment after success of the previous phase:


* `AfterPeriod`: This parameter is the same as the following setting on the Phase Settings page of the Add Phase Wizard in the console: Automatically begin this phase after a deferral period (in days) . If you specify this value, use DaysAfterPreviousPhaseSuccess to configure the period of time.


* `Manually`: This parameter is the same as the following setting on the Phase Settings page of the Add Phase Wizard in the console: Manually begin this phase of deployment .



Valid Values:

* AfterPeriod
* Manually






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[BeginConditionType]`|false   |named   |False        |



#### **Collection**

Specify an object for the target collection.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |0       |False        |



#### **CollectionId**

Specify the target collection by ID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **CollectionName**

Specify the target collection by name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **CriteriaOption**

Specify an option to choose the criteria for success of the previous phase:


* `Compliance`: This parameter is the same as the following setting on the Phase Settings page of the Add Phase Wizard in the console: Deployment success percentage . Specify the percentage value with the CriteriaValue parameter.


* `Number`: This parameter is the same as the following setting on the Phase Settings page of the Add Phase Wizard in the console: Number of devices successfully deployed . Specify the number of devices with the CriteriaValue parameter.



Valid Values:

* Compliance
* Number






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[CriteriaType]`|false   |named   |False        |



#### **CriteriaValue**

This integer value depends upon the value that you specify for CriteriaOption :


* `Compliance`: Specify the percentage


* `Number`: Specify the number of devices






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DaysAfterPreviousPhaseSuccess**

Specify an integer value for the number of days after success of the previous phase to begin this phase. This parameter is the same as the following setting on the Phase Settings page of the Add Phase Wizard in the console: Automatically begin this phase after a deferral period (in days) .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DeadlineUnit**

Specify the type of deadline period. Use this parameter with DeadlineValue .



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **DeadlineValue**

This parameter is only used if you specify `AfterPeriod` with the InstallationChoice parameter.


Specify an integer value for the period of time for the deadline. Use the DeadlineUnit parameter to specify the type of period: `Hours`, `Days`, `Weeks`, `Months`. This parameter is the same as the following setting on the Phase Settings page of the Add Phase Wizard in the console: Installation is required after this period of time .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DisableScomAlert**

This parameter is the same as the following setting on the Alerts page of the Add Phase Wizard in the console: Disable Operations Manager alerts while software updates run .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableAlert**

This parameter is the same as the following setting on the Alerts page of the Add Phase Wizard in the console: Generate an alert when the following conditions are met . When you set this parameter to `$true`, also set the following parameters:


* AlertThresholdPercentage


* AlertDelta






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableWakeOnLan**

This parameter is the same as the following setting on the Deployment Settings page of the Add Phase Wizard in the console: Use Wake-on-LAN to wake up clients for required deployments .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateScomAlertOnFailure**

This parameter is the same as the following setting on the Alerts page of the Add Phase Wizard in the console: Generate Operations Manager alert when a software update installation fails .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InstallationChoice**

Specify an option for the behavior relative to when the software is made available:


* `AsSoonAsPossible`: This parameter is the same as the following setting on the Phase Settings page of the Add Phase Wizard in the console: Installation is required as soon as possible .


* `AfterPeriod`: This parameter is the same as the following setting on the Phase Settings page of the Add Phase Wizard in the console: Installation is required after this period of time . If you specify this value, use DeadlineUnit and DeadlineValue to configure the period of time.



Valid Values:

* AsSoonAsPossible
* AfterPeriod






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[InstallationChoiceType]`|false   |named   |False        |



#### **PhaseDescription**

Specify a description for the phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PhaseName**

Specify a name for the description.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **RequirePostRebootFullScan**

This parameter is the same as the following setting on the User Experience page of the Add Phase Wizard in the console: If any update in this deployment requires a system restart, run updates deployment evaluation cycle after restart .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ServerRestartSuppression**

This parameter is the same as the following setting on the User Experience page of the Add Phase Wizard in the console. Suppress the system restart on the following devices: Servers .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SoftwareInstallation**

This parameter is the same as the following setting on the User Experience page of the Add Phase Wizard in the console: Software Installation . This setting applies when the installation deadline is reached, to allow this activity to be performed outside the maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **StateMessageVerbosity**

This parameter is the same as the following setting on the Deployment Settings page of the Add Phase Wizard in the console: State message detail level with the following values:


* `AllMessages`: All messages


* `OnlySuccessAndErrorMessages`: Only success and error messages


* `OnlyErrorMessages`: Only error messages



Valid Values:

* AllMessages
* OnlySuccessAndErrorMessages
* OnlyErrorMessages






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[VerbosityLevelType]`|false   |named   |False        |



#### **ThrottlingDays**

Specify an integer value for the number of days to gradually make this software available. This parameter is the same as the following setting on the Phase Settings page of the Add Phase Wizard in the console: Gradually make this software available over this period of time (in days) .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UseNeighborDP**

This parameter is the same as the following setting on the Download Settings page of the Add Phase Wizard in the console: Select the deployment option to use when a client uses a distribution point from a neighbor boundary group or the default site boundary group . Specify the following values:


* `$true`: Download software updates from distribution point and install


* `$false`: Do not install software updates






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UserNotificationOption**

This parameter is the same as the following setting on the User Experience page of the Add Phase Wizard in the console: Specify user experience setting for this deployment with the following values:


* `DisplayAll`: Display in Software Center and show all notifications


* `DisplaySoftwareCenterOnly`: Display in Software Center, and only show notifications for computer restarts


* `HideAll`: Hide in Software Center and all notifications



Valid Values:

* DisplayAll
* DisplaySoftwareCenterOnly
* HideAll






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[UserNotificationType]`|false   |named   |False        |



#### **UseSiteDefaultDP**

This parameter is the same as the following setting on the Download Settings page of the Add Phase Wizard in the console: When software updates are not available on any distribution points in current or neighbor boundary group, client can download and install software updates from distribution points in site default boundary group . Specify the following values:


* `$true`: Download and install software updates from the distribution points in site default boundary group


* `$false`: Do not install software updates






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WorkstationRestartSuppression**

This parameter is the same as the following setting on the User Experience page of the Add Phase Wizard in the console. Suppress the system restart on the following devices: Workstations .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WriteFilterCommit**

This parameter is the same as the following setting on the User Experience page of the Add Phase Wizard in the console: Commit changes at deadline or during a maintenance window (requires restart) . This setting applies to write filter handling for Windows Embedded devices.






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
* Microsoft.ConfigurationManager.PhasedDeploymentModel.Phase






---


### Notes




---


### Syntax
```PowerShell
New-CMSoftwareUpdatePhase [-Collection] <IResultObject> [-AlertDelta <Int32>] [-AlertThresholdPercentage <Int32>] [-AlertUnit {Hours | Days | Weeks | Months}] [-AllowMeteredConnection <Boolean>] [-AllowSystemRestart <Boolean>] [-AllowWumuFallback <Boolean>] [-BeginCondition {AfterPeriod | Manually}] [-CriteriaOption {Compliance | Number}] [-CriteriaValue <Int32>] [-DaysAfterPreviousPhaseSuccess <Int32>] [-DeadlineUnit {Hours | Days | Weeks | Months}] [-DeadlineValue <Int32>] [-DisableScomAlert <Boolean>] [-DisableWildcardHandling] [-EnableAlert <Boolean>] [-EnableWakeOnLan <Boolean>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-InstallationChoice {AsSoonAsPossible | AfterPeriod}] [-PhaseDescription <String>] -PhaseName <String> [-RequirePostRebootFullScan <Boolean>] [-ServerRestartSuppression <Boolean>] [-SoftwareInstallation <Boolean>] [-StateMessageVerbosity {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-ThrottlingDays <Int32>] [-UseNeighborDP <Boolean>] [-UserNotificationOption {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseSiteDefaultDP <Boolean>] [-WorkstationRestartSuppression <Boolean>] [-WriteFilterCommit <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdatePhase [-CollectionId] <String> [-AlertDelta <Int32>] [-AlertThresholdPercentage <Int32>] [-AlertUnit {Hours | Days | Weeks | Months}] [-AllowMeteredConnection <Boolean>] [-AllowSystemRestart <Boolean>] [-AllowWumuFallback <Boolean>] [-BeginCondition {AfterPeriod | Manually}] [-CriteriaOption {Compliance | Number}] [-CriteriaValue <Int32>] [-DaysAfterPreviousPhaseSuccess <Int32>] [-DeadlineUnit {Hours | Days | Weeks | Months}] [-DeadlineValue <Int32>] [-DisableScomAlert <Boolean>] [-DisableWildcardHandling] [-EnableAlert <Boolean>] [-EnableWakeOnLan <Boolean>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-InstallationChoice {AsSoonAsPossible | AfterPeriod}] [-PhaseDescription <String>] -PhaseName <String> [-RequirePostRebootFullScan <Boolean>] [-ServerRestartSuppression <Boolean>] [-SoftwareInstallation <Boolean>] [-StateMessageVerbosity {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-ThrottlingDays <Int32>] [-UseNeighborDP <Boolean>] [-UserNotificationOption {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseSiteDefaultDP <Boolean>] [-WorkstationRestartSuppression <Boolean>] [-WriteFilterCommit <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdatePhase [-CollectionName] <String> [-AlertDelta <Int32>] [-AlertThresholdPercentage <Int32>] [-AlertUnit {Hours | Days | Weeks | Months}] [-AllowMeteredConnection <Boolean>] [-AllowSystemRestart <Boolean>] [-AllowWumuFallback <Boolean>] [-BeginCondition {AfterPeriod | Manually}] [-CriteriaOption {Compliance | Number}] [-CriteriaValue <Int32>] [-DaysAfterPreviousPhaseSuccess <Int32>] [-DeadlineUnit {Hours | Days | Weeks | Months}] [-DeadlineValue <Int32>] [-DisableScomAlert <Boolean>] [-DisableWildcardHandling] [-EnableAlert <Boolean>] [-EnableWakeOnLan <Boolean>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-InstallationChoice {AsSoonAsPossible | AfterPeriod}] [-PhaseDescription <String>] -PhaseName <String> [-RequirePostRebootFullScan <Boolean>] [-ServerRestartSuppression <Boolean>] [-SoftwareInstallation <Boolean>] [-StateMessageVerbosity {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-ThrottlingDays <Int32>] [-UseNeighborDP <Boolean>] [-UserNotificationOption {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseSiteDefaultDP <Boolean>] [-WorkstationRestartSuppression <Boolean>] [-WriteFilterCommit <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
