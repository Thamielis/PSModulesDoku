Set-CMTaskSequencePhase
-----------------------




### Synopsis
Use this cmdlet to configure a deployment phase for a task sequence.



---


### Description

Applies to version 2006 and later. Use this cmdlet to configure a deployment phase for a task sequence. For more information, see Create phased deployments (/mem/configmgr/osd/deploy-use/create-phased-deployment-for-task-sequence).



---


### Related Links
* [Get-CMPhase](Get-CMPhase)



* [New-CMTaskSequencePhase](New-CMTaskSequencePhase)



* [Get-CMTaskSequencePhasedDeployment](Get-CMTaskSequencePhasedDeployment)



* [New-CMTaskSequenceAutoPhasedDeployment](New-CMTaskSequenceAutoPhasedDeployment)



* [New-CMTaskSequenceManualPhasedDeployment](New-CMTaskSequenceManualPhasedDeployment)



* [Remove-CMTaskSequencePhasedDeployment](Remove-CMTaskSequencePhasedDeployment)



* [Set-CMTaskSequencePhasedDeployment](Set-CMTaskSequencePhasedDeployment)



* [Get-CMPhasedDeploymentStatus](Get-CMPhasedDeploymentStatus)



* [Move-CMPhasedDeploymentToNext](Move-CMPhasedDeploymentToNext)



* [Resume-CMPhasedDeployment](Resume-CMPhasedDeployment)



* [Suspend-CMPhasedDeployment](Suspend-CMPhasedDeployment)



* [Create phased deployments](Create phased deployments)





---


### Examples
#### Example 1: Change the collection
```PowerShell
$phasedDeployment = Get-CMTaskSequencePhasedDeployment -Name "myPhasedDeployment"

$phasedDeployment | Set-CMTaskSequencePhase -Order 2 -NewCollectionId "XYZ00227"
```

#### Example 2: Move a phase up
```PowerShell
Set-CMTaskSequencePhase -PhasedDeploymentId "0bc464d9-e7dd-44c1-a157-3f8be6a79c03" -CollectionId "XYZ00227" -MovePhase MoveUp
```

#### Example 3: Configure phase settings
```PowerShell
Set-CMTaskSequencePhase -PhasedDeploymentName "myPhasedDeployment" -Name "phase1" -UserNotification HideAll -SoftwareInstallation $true -AllowSystemRestart $true -WriteFilterCommit $false -PreDownload $true -Comments "phase 1 comment" -DeploymentOption DownloadAllContentLocallyBeforeStartingTaskSequence -AllowRemoteDP $true -AllowFallback $false -CriteriaOption Compliance -CriteriaValue 90 -BeginCondition AfterPeriod -DaysAfterPreviousPhaseSuccess 3 -ThrottlingDays 5 -InstallationChoice AfterPeriod -DeadlineUnit Hours -DeadlineValue 12
```



---


### Parameters
#### **AllowFallback**

This parameter is the same as the following setting on the Distribution Points page of the Add Phase Wizard in the console: Allow clients to use distribution points from the default site boundary group .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowRemoteDP**

This parameter is the same as the following setting on the Distribution Points page of the Add Phase Wizard in the console: When no local distribution point is available, use a remote distribution point .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowSystemRestart**

This parameter is the same as the following setting on the User Experience page of the Add Phase Wizard in the console: System restart (if required to complete installation) . This setting applies when the installation deadline is reached, to allow this activity to be performed outside the maintenance window.






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

Specify an object for the target collection






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify the target collection by ID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the target collection by name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comments**

Specify optional comments for this phase. The maximum length is 512 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **DeploymentOption**

This parameter is the same as the following setting on the Distribution Points page of the Add Phase Wizard in the console: Select the deployment option to use when a client uses a distribution point from a neighbor boundary group or the default site boundary group . It accepts the following values:


* `DownloadContentLocallyWhenNeededByRunningTaskSequence`: Download content locally when needed by the running task sequence


* `DownloadAllContentLocallyBeforeStartingTaskSequence`: Download all content locally before starting task sequence



Valid Values:

* DownloadContentLocallyWhenNeededByRunningTaskSequence
* DownloadAllContentLocallyBeforeStartingTaskSequence
* RunFromDistributionPoint






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[DeploymentOptionType]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the phase to configure.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |PhaseId|



#### **InputObject**

Specify a phased deployment object that includes the phase to configure.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |0       |True (ByValue)|PhasedDeployment|



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



#### **MovePhase**

Change the order for the selected phase. You can move it up one, move it down one, or move to a specific index. If you specify `MoveToOrder`, use the -MoveToOrder parameter to set the specific index.



Valid Values:

* MoveUp
* MoveDown
* MoveToOrder






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ReorderType]`|false   |named   |False        |



#### **MoveToOrder**

When you set the -MovePhase parameter to `MoveToOrder`, use this parameter to set the specific index.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Name**

Specify the name of the phase to configure.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|false   |named   |False        |PhaseName|



#### **NewCollection**

Specify a collection object to use as the new target for the selected phase.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **NewCollectionId**

Specify a collection by ID to use as the new target for the selected phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NewCollectionName**

Specify a collection by name to use as the new target for the selected phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NewPhaseName**

Use this parameter to rename the selected phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Order**

Specify the index of the phase to configure.






|Type     |Required|Position|PipelineInput|Aliases   |
|---------|--------|--------|-------------|----------|
|`[Int32]`|false   |named   |False        |PhaseOrder|



#### **PhasedDeploymentId**

Select the phased deployment by ID. Then use other parameters to select the specific phase in that deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **PhasedDeploymentName**

Select the phased deployment by name. Then use other parameters to select the specific phase in that deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **PreDownload**

This parameter is the same as the following setting on the General page of the Add Phase Wizard in the console: Pre-download content for this task sequence .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SoftwareInstallation**

This parameter is the same as the following setting on the User Experience page of the Add Phase Wizard in the console: Software Installation . This setting applies when the installation deadline is reached, to allow this activity to be performed outside the maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ThrottlingDays**

Specify an integer value for the number of days to gradually make this software available. This parameter is the same as the following setting on the Phase Settings page of the Add Phase Wizard in the console: Gradually make this software available over this period of time (in days) .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UserNotification**

This parameter is the same as the following setting on the User Experience page of the Add Phase Wizard in the console: Specify user experience setting for this deployment with the following values:


* `DisplayAll`: Display in Software Center and show all notifications


* `HideAll`: Hide in Software Center and all notifications



Valid Values:

* DisplayAll
* DisplaySoftwareCenterOnly
* HideAll






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[UserNotificationType]`|false   |named   |False        |



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_PhasedDeployment






---


### Notes




---


### Syntax
```PowerShell
Set-CMTaskSequencePhase [-InputObject] <IResultObject> [-AllowFallback <Boolean>] [-AllowRemoteDP <Boolean>] [-AllowSystemRestart <Boolean>] [-BeginCondition {AfterPeriod | Manually}] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comments <String>] [-CriteriaOption {Compliance | Number}] [-CriteriaValue <Int32>] [-DaysAfterPreviousPhaseSuccess <Int32>] [-DeadlineUnit {Hours | Days | Weeks | Months}] [-DeadlineValue <Int32>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [-InstallationChoice {AsSoonAsPossible | AfterPeriod}] [-MovePhase {MoveUp | MoveDown | MoveToOrder}] [-MoveToOrder <Int32>] [-Name <String>] [-NewCollection <IResultObject>] [-NewCollectionId <String>] [-NewCollectionName <String>] [-NewPhaseName <String>] [-Order <Int32>] [-PreDownload <Boolean>] [-SoftwareInstallation <Boolean>] [-ThrottlingDays <Int32>] [-UserNotification {DisplayAll | HideAll}] [-WriteFilterCommit <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequencePhase [-PhasedDeploymentId] <String> [-AllowFallback <Boolean>] [-AllowRemoteDP <Boolean>] [-AllowSystemRestart <Boolean>] [-BeginCondition {AfterPeriod | Manually}] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comments <String>] [-CriteriaOption {Compliance | Number}] [-CriteriaValue <Int32>] [-DaysAfterPreviousPhaseSuccess <Int32>] [-DeadlineUnit {Hours | Days | Weeks | Months}] [-DeadlineValue <Int32>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [-InstallationChoice {AsSoonAsPossible | AfterPeriod}] [-MovePhase {MoveUp | MoveDown | MoveToOrder}] [-MoveToOrder <Int32>] [-Name <String>] [-NewCollection <IResultObject>] [-NewCollectionId <String>] [-NewCollectionName <String>] [-NewPhaseName <String>] [-Order <Int32>] [-PreDownload <Boolean>] [-SoftwareInstallation <Boolean>] [-ThrottlingDays <Int32>] [-UserNotification {DisplayAll | HideAll}] [-WriteFilterCommit <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequencePhase [-PhasedDeploymentName] <String> [-AllowFallback <Boolean>] [-AllowRemoteDP <Boolean>] [-AllowSystemRestart <Boolean>] [-BeginCondition {AfterPeriod | Manually}] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comments <String>] [-CriteriaOption {Compliance | Number}] [-CriteriaValue <Int32>] [-DaysAfterPreviousPhaseSuccess <Int32>] [-DeadlineUnit {Hours | Days | Weeks | Months}] [-DeadlineValue <Int32>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [-InstallationChoice {AsSoonAsPossible | AfterPeriod}] [-MovePhase {MoveUp | MoveDown | MoveToOrder}] [-MoveToOrder <Int32>] [-Name <String>] [-NewCollection <IResultObject>] [-NewCollectionId <String>] [-NewCollectionName <String>] [-NewPhaseName <String>] [-Order <Int32>] [-PreDownload <Boolean>] [-SoftwareInstallation <Boolean>] [-ThrottlingDays <Int32>] [-UserNotification {DisplayAll | HideAll}] [-WriteFilterCommit <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
