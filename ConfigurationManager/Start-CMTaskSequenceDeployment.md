Start-CMTaskSequenceDeployment
------------------------------




### Synopsis
(Deprecated) Start a task sequence deployment.



---


### Description

> [!IMPORTANT] > This cmdlet is deprecated. Use New-CMTaskSequenceDeployment (New-CMTaskSequenceDeployment.md)instead.



Use this cmdlet to start a task sequence deployment. A task sequence deployment assigns a task sequence to a collection of computers. For more information, see Deploy a task sequence in Configuration Manager (/mem/configmgr/osd/deploy-use/deploy-a-task-sequence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequenceDeployment](New-CMTaskSequenceDeployment)



* [Get-CMTaskSequenceDeployment](Get-CMTaskSequenceDeployment)



* [Set-CMTaskSequenceDeployment](Set-CMTaskSequenceDeployment)



* [Remove-CMTaskSequenceDeployment](Remove-CMTaskSequenceDeployment)



* [Deploy a task sequence in Configuration Manager](Deploy a task sequence in Configuration Manager)





---


### Examples
#### Example 1: Start a task sequence deployment with default options
```PowerShell
Get-CMTaskSequence -Name "Upgrade Windows 10" | Start-CMTaskSequenceDeployment -CollectionName "Collection 01"
```

#### Example 2: Start a task sequence deployment with configured options
```PowerShell
Start-CMTaskSequenceDeployment -TaskSequencePackageId "XYZ00003" -CollectionName "Collection 02" -Comment "Task sequence test" -DeployPurpose Required -SendWakeUpPacket $True -UseMeteredNetwork $True -ScheduleEvent AsSoonAsPossible -RerunBehavior NeverRerunDeployedProgram -RunFromSoftwareCenter $True -ShowTaskSequenceProgress $False -SoftwareInstallation $True -SystemRestart $True -PersistOnWriteFilterDevice $False -AllowFallback $True -DeploymentOption DownloadAllContentLocallyBeforeStartingTaskSequence -AllowSharedContent $True -InternetOption $True
```



---


### Parameters
#### **AlertDateTime**

When you configure the deployment to create an alert for successful deployment, use this parameter to specify a DateTime object. Configuration Manager creates a deployment alert when the threshold is lower than the PercentSuccess after this date.


To get this object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)built-in cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **AlertDay**

This parameter is deprecated. Use AlertDateTime .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **AlertTime**

This parameter is deprecated. Use AlertDateTime .






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


If you specify `Clients`, the default value for the DeploymentOption parameter is `DownloadAllContentLocallyBeforeStartingTaskSequence`. If you specify `ClientsMediaAndPxe`, `MediaAndPxe`, or `MediaAndPxeHidden`, the default value for the DeploymentOption parameter is `DownloadContentLocallyWhenNeededByRunningTaskSequence`.



Valid Values:

* Clients
* ClientsMediaAndPxe
* MediaAndPxe
* MediaAndPxeHidden






|Type                   |Required|Position|PipelineInput|Aliases        |
|-----------------------|--------|--------|-------------|---------------|
|`[MakeAvailableToType]`|false   |named   |False        |MakeAvailableTo|



#### **Collection**

Specify a collection object to which this task sequence is deployed. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify the ID of the collection to which this task sequence is deployed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the name of the collection to which this task sequence is deployed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specify an optional comment for the task sequence deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentAvailableDateTime**

Specify a DateTime object for when this deployment is available . To get this object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)built-in cmdlet.


Use DeploymentExpireDateTime to specify when the deployment expires , and Schedule to specify the deployment assignment, or deadline .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentAvailableDay**

This parameter is deprecated. Use DeploymentAvailableDateTime .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentAvailableTime**

This parameter is deprecated. Use DeploymentAvailableDateTime .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentExpireDateTime**

Specify a DateTime object for when this deployment expires . To get this object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)built-in cmdlet.


Use DeploymentAvailableDateTime to specify when the deployment is available , and Schedule to specify the deployment assignment, or deadline .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentExpireDay**

This parameter is deprecated. Use DeploymentExpireDateTime .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentExpireTime**

This parameter is deprecated. Use DeploymentExpireDateTime .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentOption**

Specify how clients interact with the distribution points to get content for the task sequence. Not all options are available in specific scenarios. For more information, see Deploy a task sequence - Deployment options (/mem/configmgr/osd/deploy-use/deploy-a-task-sequence#bkmk_deploy-options).


If you specify `Clients` for the Availability parameter, the default value for this parameter is `DownloadAllContentLocallyBeforeStartingTaskSequence`. If you specify `ClientsMediaAndPxe`, `MediaAndPxe`, or `MediaAndPxeHidden` for the Availability parameter, the default value for this parameter is `DownloadContentLocallyWhenNeededByRunningTaskSequence`.



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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a task sequence deployment object. To get this object, use the Get-CMTaskSequenceDeployment (Get-CMTaskSequenceDeployment.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **InternetOption**

Indicates whether the task sequence runs on clients connecting over the internet.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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


Use AvailableDateTime to specify when the deployment is available , and DeadlineDateTime to specify when the deployment expires .


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






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |0       |False        |PackageId|



#### **UseMeteredNetwork**

Indicates whether to allow clients on a metered internet connection to download content after the installation deadline, which might incur extra costs.






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
Start-CMTaskSequenceDeployment [-InputObject] <IResultObject> [-AlertDateTime <DateTime>] [-AlertDay <DateTime>] [-AlertTime <DateTime>] [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-Availability {Clients | ClientsMediaAndPxe | MediaAndPxe | MediaAndPxeHidden}] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentExpireDay <DateTime>] [-DeploymentExpireTime <DateTime>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence | RunFromDistributionPoint}] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InternetOption <Boolean>] [-PassThru] [-PercentFailure <Int32>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-ShowTaskSequenceProgress <Boolean>] [-SoftwareInstallation <Boolean>] [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMTaskSequenceDeployment [-TaskSequencePackageId] <String> [-AlertDateTime <DateTime>] [-AlertDay <DateTime>] [-AlertTime <DateTime>] [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-Availability {Clients | ClientsMediaAndPxe | MediaAndPxe | MediaAndPxeHidden}] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentExpireDay <DateTime>] [-DeploymentExpireTime <DateTime>] [-DeploymentOption {DownloadContentLocallyWhenNeededByRunningTaskSequence | DownloadAllContentLocallyBeforeStartingTaskSequence | RunFromDistributionPoint}] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InternetOption <Boolean>] [-PassThru] [-PercentFailure <Int32>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-ShowTaskSequenceProgress <Boolean>] [-SoftwareInstallation <Boolean>] [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
