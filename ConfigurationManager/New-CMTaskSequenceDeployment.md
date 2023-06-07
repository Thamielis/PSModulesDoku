New-CMTaskSequenceDeployment
----------------------------




### Synopsis
Create a task sequence deployment.



---


### Description

The New-CMTaskSequenceDeployment cmdlet creates a task sequence deployment. A task sequence deployment assigns a task sequence to a collection of computers.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTaskSequenceDeployment](Get-CMTaskSequenceDeployment)



* [Set-CMTaskSequenceDeployment](Set-CMTaskSequenceDeployment)



* [Remove-CMTaskSequenceDeployment](Remove-CMTaskSequenceDeployment)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [Deploy a task sequence](Deploy a task sequence)





---


### Examples
#### Example 1: Deploy a task sequence with many common parameters
```PowerShell
$DeployTS = Get-CMTaskSequence -TaskSequencePackageId 'PS104823'
$DeployCollection = 'PS11B7C4'
$DeployAvailableTime = [datetime]::ParseExact("20251125-200000", "yyyyMMdd-HHmmss", $null)
$DeployExpireTime = [datetime]::ParseExact("20260125-200000", "yyyyMMdd-HHmmss", $null)
$ScheduleDateTime = [datetime]::ParseExact("20251225-200000", "yyyyMMdd-HHmmss", $null)
$DeploySchedule = New-CMSchedule -DurationInterval Days -RecurInterval Days -RecurCount 1 -DurationCount 0 -Start $ScheduleDateTime
New-CMTaskSequenceDeployment -InputObject $DeployTS -DeployPurpose Required -AvailableDateTime $DeployAvailableTime -Availability Clients -RerunBehavior AlwaysRerunProgram -Schedule $DeploySchedule -CollectionId $DeployCollection -ShowTaskSequenceProgress $true -DeploymentOption DownloadAllContentLocallyBeforeStartingTaskSequence -RunFromSoftwareCenter $true -DeadlineDateTime $DeployExpireTime
```



---


### Parameters
#### **AlertDateTime**

If you enable a deployment alert, use this parameter to specify a time for the alert.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **AllowFallback**

Allow clients to use distribution points from the default site boundary group.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowSharedContent**

Allow clients to use distribution points from a neighbor boundary group.






|Type       |Required|Position|PipelineInput|Aliases                        |
|-----------|--------|--------|-------------|-------------------------------|
|`[Boolean]`|false   |named   |False        |AllowUseRemoteDistributionPoint|



#### **Availability**

Specify whether to make this task sequence available to Configuration Manager clients, and whether it's available to run when you deploy an OS by using boot media, prestaged media, or PXE.



Valid Values:

* Clients
* ClientsMediaAndPxe
* MediaAndPxe
* MediaAndPxeHidden






|Type                   |Required|Position|PipelineInput|Aliases        |
|-----------------------|--------|--------|-------------|---------------|
|`[MakeAvailableToType]`|false   |named   |False        |MakeAvailableTo|



#### **AvailableDateTime**

Specify when this deployment is available .


Use -DeadlineDateTime to specify when the deployment expires , and -Schedule to specify the deployment assignment, or deadline .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **Collection**

Specify a collection object as the target for this task sequence deployment. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify a collection ID as the target for this task sequence deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify a collection name as the target for this task sequence deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specify an optional comment for the task sequence deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeadlineDateTime**

Use this parameter to specify when the deployment expires .


Use -AvailableDateTime to specify when the deployment is available , and -Schedule to specify the deployment assignment, or deadline .






|Type        |Required|Position|PipelineInput|Aliases                 |
|------------|--------|--------|-------------|------------------------|
|`[DateTime]`|false   |named   |False        |DeploymentExpireDateTime|



#### **DeploymentOption**

Specify how clients interact with the distribution points to get content for the task sequence. Not all options are available in specific scenarios. For more information, see Deploy a task sequence - Deployment options (/mem/configmgr/osd/deploy-use/deploy-a-task-sequence#bkmk_deploy-options).



Valid Values:

* DownloadContentLocallyWhenNeededByRunningTaskSequence
* DownloadAllContentLocallyBeforeStartingTaskSequence
* RunFromDistributionPoint






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[DeploymentOptionType]`|false   |named   |False        |



#### **DeployPurpose**

Specify whether this deployment is available for users to install, or it's required to install at the deadline.



Valid Values:

* Available
* Required






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[DeployPurposeType]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributeCollectionName**

The site distributes content to the distribution point groups that are associated with this collection name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DistributeContent**

Add this parameter to distribute the task sequence content when you create this deployment. Clients can't install the task sequence until you distribute content to distribution points that the clients can access.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPointGroupName**

The site distributes content to this distribution point group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DistributionPointName**

The site distributes content to this distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a task sequence object to deploy. To get a task sequence object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |0       |True (ByValue)|TaskSequence|



#### **InternetOption**

Allow the task sequence to run for clients on the internet.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PercentFailure**

If you create an alert for failed deployments, the site generates an alert when the percentage of failed deployments is higher than this number.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PercentSuccess**

If you create an alert for successful deployments, the site generates an alert when the percentage of successful deployments is lower than this number.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PersistOnWriteFilterDevice**

Configure how the client handles the write filter on Windows Embedded devices.


* `$true`: Commit changes at the deadline or during a maintenance window. A restart is required.


* `$false`: Apply content on the overlay and commit later.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RerunBehavior**

Specify whether the task sequence reruns on a computer if it previously ran before the scheduled mandatory time. By default, the task sequence always reruns.



Valid Values:

* NeverRerunDeployedProgram
* AlwaysRerunProgram
* RerunIfFailedPreviousAttempt
* RerunIfSucceededOnPreviousAttempt






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[RerunBehaviorType]`|false   |named   |False        |



#### **RunFromSoftwareCenter**

Allow users to run the program independently of assignments.






|Type       |Required|Position|PipelineInput|Aliases                   |
|-----------|--------|--------|-------------|--------------------------|
|`[Boolean]`|false   |named   |False        |AllowUsersRunIndependently|



#### **Schedule**

Use this parameter to specify the deployment assignment, or deadline .


Use -AvailableDateTime to specify when the deployment is available , and -DeadlineDateTime to specify when the deployment expires .


Specify an array of schedule objects. A schedule object defines the mandatory assignment schedule for a deployment. To create a schedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






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

When the installation deadline is reached, set this parameter to `$true` to allow the task sequence to install outside the maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SystemRestart**

When the installation deadline is reached, set this parameter to `$true` to allow system restart if necessary outside the maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **TaskSequencePackageId**

Specify the ID of the task sequence to deploy.






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[String]`|true    |0       |False        |PackageId<br/>TaskSequenceId|



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
Make sure to use the schedule parameters appropriately:

- -AvailableDateTime : Specify when this deployment is available .

- -DeadlineDateTime : Specify when the deployment expires .

- -Schedule : Specify the deployment assignment, or deadline .



---


### Syntax
```PowerShell
New-CMTaskSequenceDeployment [-InputObject] <IResultObject> [-AlertDateTime <DateTime>] [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-Availability {Clients | ClientsMediaAndPxe | MediaAndPxe | MediaAndPxeHidden}] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence | RunFromDistributionPoint}] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-ForceWildcardHandling] [-InternetOption <Boolean>] [-PercentFailure <Int32>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-ShowTaskSequenceProgress <Boolean>] [-SoftwareInstallation <Boolean>] [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequenceDeployment [-TaskSequencePackageId] <String> [-AlertDateTime <DateTime>] [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-Availability {Clients | ClientsMediaAndPxe | MediaAndPxe | MediaAndPxeHidden}] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence | RunFromDistributionPoint}] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-ForceWildcardHandling] [-InternetOption <Boolean>] [-PercentFailure <Int32>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-ShowTaskSequenceProgress <Boolean>] [-SoftwareInstallation <Boolean>] [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
