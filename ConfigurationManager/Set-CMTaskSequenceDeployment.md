Set-CMTaskSequenceDeployment
----------------------------




### Synopsis
Configure a task sequence deployment.



---


### Description

The Set-CMTaskSequenceDeployment cmdlet configures a task sequence deployment. A task sequence deployment assigns a task sequence to a collection of computers.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequenceDeployment](New-CMTaskSequenceDeployment)



* [Get-CMTaskSequenceDeployment](Get-CMTaskSequenceDeployment)



* [Remove-CMTaskSequenceDeployment](Remove-CMTaskSequenceDeployment)



* [New-CMSchedule](New-CMSchedule)



* [Get-CMTaskSequence](Get-CMTaskSequence)





---


### Examples
#### Example 1: Configure a deployment to show progress
```PowerShell
Set-CMTaskSequenceDeployment -TaskSequenceName "Task Sequence 1333" -CollectionName "All Systems" -Comment "Task sequence test" -ShowTaskSequenceProgress $True
```

#### Example 2: Reconfigure a task sequence deployment
```PowerShell
Set-CMTaskSequenceDeployment -TaskSequenceName "Task Sequence 1333" -CollectionName "All Desktop and Server Clients" -Comment "Task sequence test" -SendWakeupPacket $True -UseMeteredNetwork $True -DeploymentExpireDateTime $(Get-Date) -ScheduleEvent LogOff -RerunBehavior NeverRerunDeployedProgram -AllowUsersRunIndependently $True -ShowTaskSequenceProgress $False -SoftwareInstallation $True -SystemRestart $True -PersistOnWriteFilterDevice $False -InternetOption $True -DeploymentOption DownloadAllContentLocallyBeforeStartingTaskSequence -AllowFallback $True -AllowSharedContent $True
```



---


### Parameters
#### **AddSchedule**

Specify a schedule token object to add to the deployment. To create a schedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **AddScheduleEvent**

Specify one of the accepted schedule events to add to the deployment.



Valid Values:

* AsSoonAsPossible
* LogOn
* LogOff






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ScheduleEventType[]]`|false   |named   |False        |



#### **AlertDateTime**

Specifies an alert date time.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **AllowFallback**

Indicates whether to allow clients to use a fallback source location for content.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowSharedContent**

Indicates whether to allow shared content.






|Type       |Required|Position|PipelineInput|Aliases                        |
|-----------|--------|--------|-------------|-------------------------------|
|`[Boolean]`|false   |named   |False        |AllowUseRemoteDistributionPoint|



#### **AllowUsersRunIndependently**

Indicates whether to allow users to independently run the program, regardless of its assignment status.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClearSchedule**

Add this parameter to remove all schedules from the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClearScheduleEvent**

Add this parameter to remove all schedule events from the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Collection**

Specifies a collection object as the target of the deployment.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specifies the ID of a collection as the target of the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specifies a name of a collection designated to receive a task sequence deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specifies a optional comment for the task sequence deployment to help describe it.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CreateAlertOnFailure**

Indicates whether to create an alert on failure.






|Type       |Required|Position|PipelineInput|Aliases                        |
|-----------|--------|--------|-------------|-------------------------------|
|`[Boolean]`|false   |named   |False        |CreateAlertBaseOnPercentFailure|



#### **CreateAlertOnSuccess**

Indicates whether to create an alert on success.






|Type       |Required|Position|PipelineInput|Aliases                        |
|-----------|--------|--------|-------------|-------------------------------|
|`[Boolean]`|false   |named   |False        |CreateAlertBaseOnPercentSuccess|



#### **DeploymentAvailableDateTime**

Specifies deployment available date time.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentExpireDateTime**

Specifies deployment expire date time.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentOption**

Specifies if clients download all content before starting the task sequence, or download content as needed by the running task sequence.



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

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a task sequence deployment object. To get a task sequence object, use the Get-CMTaskSequenceDeployment (Get-CMTaskSequenceDeployment.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                                                            |
|-----------------|--------|--------|--------------|-------------------------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Deployment<br/>DeploymentSummary<br/>TaskSequence<br/>Advertisement|



#### **InternetOption**

Indicates whether the task sequence runs on clients connecting over the internet.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MakeAvailableTo**

Specifies whether to make this task sequence available to Configuration Manager clients, and whether to make it available when you deploy an OS by using boot media, prestaged media, or PXE.



Valid Values:

* Clients
* ClientsMediaAndPxe
* MediaAndPxe
* MediaAndPxeHidden






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[MakeAvailableToType]`|false   |named   |False        |



#### **PassThru**

Returns the current working object. By default, this cmdlet doesn't generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PercentFailure**

Specifies a threshold percentage for failed task sequence deployment.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PercentSuccess**

Specifies a threshold percentage for successful task sequence deployment.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PersistOnWriteFilterDevice**

Indicates whether to install a task sequence on the temporary overlay and commit changes later, or commit the changes at an installation deadline or a maintenance window. This setting applies to devices running an embedded edition of Windows with a write filter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RemoveSchedule**

Specify a schedule token object to remove from the deployment. To create a schedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **RemoveScheduleEvent**

Specify one of the accepted schedule events to remove from the deployment.



Valid Values:

* AsSoonAsPossible
* LogOn
* LogOff






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ScheduleEventType[]]`|false   |named   |False        |



#### **RerunBehavior**

Specifies whether the task sequence will rerun on a computer if it previously ran before the scheduled mandatory time. By default, the task sequence always reruns.



Valid Values:

* NeverRerunDeployedProgram
* AlwaysRerunProgram
* RerunIfFailedPreviousAttempt
* RerunIfSucceededOnPreviousAttempt






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[RerunBehaviorType]`|false   |named   |False        |



#### **Schedule**

Specifies an array of CMSchedule objects. A CMSchedule object defines the mandatory assignment schedule for a deployment. To create a CMSchedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **ScheduleEvent**

Specifies an array of events that determine when the task sequence deployment runs.



Valid Values:

* AsSoonAsPossible
* LogOn
* LogOff






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ScheduleEventType[]]`|false   |named   |False        |



#### **SendWakeupPacket**

Indicates whether to send a wake-up packet to computers before the deployment begins. If this value is `$True`, Configuration Manager wakes a computer from sleep. If this value is `$False`, it doesn't wake computers from sleep. For computers to wake, first configure Wake On LAN.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ShowTaskSequenceProgress**

Indicates whether to show a process dialog for a task sequence.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SoftwareInstallation**

Indicates whether to allow the application to install, even if the installation occurs outside of a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SystemRestart**

Indicates whether to allow an advertised program to restart the system, even if the restart occurs outside of a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **TaskSequenceDeploymentId**

Specifies an ID for a task sequence deployment to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TaskSequenceName**

Specifies a name for the task sequence to deploy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TaskSequencePackageId**

Specifies an ID for a task sequence to deploy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **UseMeteredNetwork**

Indicates whether to allow clients on a metered internet connection to download content after the installation deadline, which might incur additional costs.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseUtcForAvailableSchedule**

Indicates whether client computers use UTC time to determine the availability of a program. UTC time makes the task sequence available at the same time for all computers.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseUtcForExpireSchedule**

Indicates whether client computers use UTC time to determine the expiration of a program. UTC time makes the task sequence available at the same time for all computers.






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
* IResultObject#SMS_Advertisement






---


### Notes




---


### Syntax
```PowerShell
Set-CMTaskSequenceDeployment [-AddSchedule <IResultObject[]>] [-AddScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-AlertDateTime <DateTime>] [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-AllowUsersRunIndependently <Boolean>] [-ClearSchedule] [-ClearScheduleEvent] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-CreateAlertOnFailure <Boolean>] [-CreateAlertOnSuccess <Boolean>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence | RunFromDistributionPoint}] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-InternetOption <Boolean>] [-MakeAvailableTo {Clients | ClientsMediaAndPxe | MediaAndPxe | MediaAndPxeHidden}] [-PassThru] [-PercentFailure <Int32>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-RemoveSchedule <IResultObject[]>] [-RemoveScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-ShowTaskSequenceProgress <Boolean>] [-SoftwareInstallation <Boolean>] [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceDeployment [-AddSchedule <IResultObject[]>] [-AddScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-AlertDateTime <DateTime>] [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-AllowUsersRunIndependently <Boolean>] [-ClearSchedule] [-ClearScheduleEvent] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-CreateAlertOnFailure <Boolean>] [-CreateAlertOnSuccess <Boolean>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence | RunFromDistributionPoint}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InternetOption <Boolean>] [-MakeAvailableTo {Clients | ClientsMediaAndPxe | MediaAndPxe | MediaAndPxeHidden}] [-PassThru] [-PercentFailure <Int32>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-RemoveSchedule <IResultObject[]>] [-RemoveScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-ShowTaskSequenceProgress <Boolean>] [-SoftwareInstallation <Boolean>] [-SystemRestart <Boolean>] -TaskSequenceDeploymentId <String> [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceDeployment [-AddSchedule <IResultObject[]>] [-AddScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-AlertDateTime <DateTime>] [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-AllowUsersRunIndependently <Boolean>] [-ClearSchedule] [-ClearScheduleEvent] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-CreateAlertOnFailure <Boolean>] [-CreateAlertOnSuccess <Boolean>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence | RunFromDistributionPoint}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InternetOption <Boolean>] [-MakeAvailableTo {Clients | ClientsMediaAndPxe | MediaAndPxe | MediaAndPxeHidden}] [-PassThru] [-PercentFailure <Int32>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-RemoveSchedule <IResultObject[]>] [-RemoveScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-ShowTaskSequenceProgress <Boolean>] [-SoftwareInstallation <Boolean>] [-SystemRestart <Boolean>] -TaskSequenceName <String> [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMTaskSequenceDeployment [-AddSchedule <IResultObject[]>] [-AddScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-AlertDateTime <DateTime>] [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-AllowUsersRunIndependently <Boolean>] [-ClearSchedule] [-ClearScheduleEvent] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-CreateAlertOnFailure <Boolean>] [-CreateAlertOnSuccess <Boolean>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence | RunFromDistributionPoint}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InternetOption <Boolean>] [-MakeAvailableTo {Clients | ClientsMediaAndPxe | MediaAndPxe | MediaAndPxeHidden}] [-PassThru] [-PercentFailure <Int32>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-RemoveSchedule <IResultObject[]>] [-RemoveScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-ShowTaskSequenceProgress <Boolean>] [-SoftwareInstallation <Boolean>] [-SystemRestart <Boolean>] -TaskSequencePackageId <String> [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
