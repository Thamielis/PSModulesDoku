Set-CMPackageDeployment
-----------------------




### Synopsis
Changes values that define how Configuration Manager deploys a software package.



---


### Description

The Set-CMPackageDeployment cmdlet changes values that define how Configuration Manager deploys a software package. A deployment includes a collection of devices or users, a package to deploy, and either a device program name or a standard program name. To specify which deployment to modify, specify the collection name, package, and program name. You can specify the package by name or ID, or you can use the Get-CMPackage (Get-CMPackage.md)cmdlet to get a package object.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMPackageDeployment](New-CMPackageDeployment)



* [Get-CMPackageDeployment](Get-CMPackageDeployment)



* [Get-CMPackageDeploymentStatus](Get-CMPackageDeploymentStatus)



* [Remove-CMPackageDeployment](Remove-CMPackageDeployment)



* [Get-CMPackage](Get-CMPackage)





---


### Examples
#### Example 1: Set recurrence properties
```PowerShell
PS XYZ:\> Set-CMPackageDeployment -CollectionName "All Systems" -DeviceProgramName "DPM" -PackageName "User State Migration Tool for Windows 8" -RecurUnit Hours -RecurValue 7 -UseRecurrencePattern $True
```
This command makes changes to the deployment specified by the collection named All Systems, the device program named DPM, and the package named User State Migration Tool for Windows 8. The command sets the UseRecurrencePattern parameter to a value of $True. The command specifies a recur unit of Hours and a recur value of seven. Therefore, the deployment recurs every seven hours.
#### Example 2: Set availability day and time
```PowerShell
PS XYZ:\> Set-CMPackageDeployment -CollectionName "All Systems" -PackageName "User State Migration Tool for Windows 8" -StandardProgramName "SPM" -DeploymentAvailableDay 2012/10/18 -DeploymentAvailableTime 15:41 -UseUtcForAvailableSchedule $False
```
This command makes changes to the deployment specified by the collection named All Systems, the package named User State Migration Tool for Windows 8, and the standard program named SPM. The command specifies a day and time when the deployment becomes available. The command also specifies that the deployment does not use UTC for the availability schedule. The schedule refers to the local time zone.


---


### Parameters
#### **AllowFallback**

{{ Fill AllowFallback Description }}






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowSharedContent**

Indicates whether clients use shared content. If this value is $True, clients attempt to download content from other clients that downloaded that content. If this value is $False, clients do not attempt to download from other clients.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Collection**

Specifies the user collection.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specifies the ID of a device or user collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specifies the ID of a device or user collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specifies a comment for the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentAvailableDateTime**

Specifies, as a DateTime object, the date and time that the deployment becomes available. To obtain a DateTime object, use the Get-Date cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentExpireDateTime**

Specifies, as a DateTime object, the date and time that the deployment expires. To obtain a DateTime object, use the Get-Date cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentStartDateTime**

Specifies, as a DateTime object, the date and time that the deployment starts. To obtain a DateTime object, use the Get-Date cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeviceProgramName**

Specifies the name of a device program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableExpireSchedule**

Indicates whether to enable the schedule to expire the deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **FastNetworkOption**

Specifies client behavior on a fast network. The acceptable values for this parameter are:


* DownloadContentFromDistributionPointAndRunLocally


* RunProgramFromDistributionPoint



Valid Values:

* RunProgramFromDistributionPoint
* DownloadContentFromDistributionPointAndRunLocally






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[FastNetworkOptionType]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a package object.






|Type             |Required|Position|PipelineInput |Aliases                                        |
|-----------------|--------|--------|--------------|-----------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Package<br/>DeploymentSummary<br/>Advertisement|



#### **PackageId**

Specifies the ID of a package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageName**

Specifies the name of a package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns the current working object. By default, this cmdlet does not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PersistOnWriteFilterDevice**

Indicates whether to enable write filters for embedded devices. For a value of $True, the device commits changes during a maintenance window. This action requires a restart. For a value of $False, the device saves changes in an overlay and commits them later.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RecurUnit**

Specifies a unit for a recurring deployment. The acceptable values for this parameter are:


* Days


* Hours


* Minutes



Valid Values:

* Minutes
* Hours
* Days






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[RecurUnitType]`|false   |named   |False        |



#### **RecurValue**

Specifies how often a deployment recurs. This parameter depends on the unit type specified in the RecurUnit parameter. This value can be between 1 and 23 if the unit is Hours, between 1 and 31 if the unit is Days, or between 1 and 59 if the unit is Minutes.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Rerun**

Indicates whether the deployment reruns. If this value is $True, the deployment runs again for clients as specified in the RerunBehavior parameter. If this value is $False, the deployment does not run again.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RerunBehavior**

Specifies how a deployment reruns on a client. The acceptable values for this parameter are:


* AlwaysRerunProgram. Rerun as scheduled, even if the deployment succeeded. You can use this value for recurring deployments. - NeverRerunDeployedProgram. Does not rerun, even if the deployment failed or files changed. - RerunIfFailedPreviousAttempt. Rerun, as scheduled, if the deployment failed on the previous attempt. - RerunIfSucceededOnpreviousAttempt. Rerun only if the previous attempt succeeded. You can use this value for updates that depend on the previous update.



Valid Values:

* NeverRerunDeployedProgram
* AlwaysRerunProgram
* RerunIfFailedPreviousAttempt
* RerunIfSucceededOnPreviousAttempt






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[RerunBehaviorType]`|false   |named   |False        |



#### **RunFromSoftwareCenter**

Indicates whether to run from software center.






|Type       |Required|Position|PipelineInput|Aliases                   |
|-----------|--------|--------|-------------|--------------------------|
|`[Boolean]`|false   |named   |False        |AllowUsersRunIndependently|



#### **Schedule**

Specifies a CMSchedule object. The schedule specifies when the maintenance window occurs. To create a CMSchedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|false   |named   |False        |



#### **ScheduleEvent**

Specifies an array of schedule event types. The acceptable values for this parameter are:


* AsSoonAsPossible


* LogOff


* LogOn


* SendWakeUpPacket



Valid Values:

* AsSoonAsPossible
* LogOn
* LogOff






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ScheduleEventType[]]`|false   |named   |False        |



#### **SendWakeupPacket**

Indicates whether to send a wake-up packet to computers before the deployment begins. If this value is $True, Configuration Manager wakes a computer from sleep. If this value is $False, it does not wake computers from sleep. For computers to wake, you must first configure Wake On LAN.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SlowNetworkOption**

Specifies how Configuration Manager deploys this package in a slow network. The acceptable values for this parameter are:


* DoNotRunProgram


* DownloadContentFromDistributionPointAndLocally


* RunProgramFromDistributionPoint



Valid Values:

* DoNotRunProgram
* DownloadContentFromDistributionPointAndLocally
* RunProgramFromDistributionPoint






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[SlowNetworkOptionType]`|false   |named   |False        |



#### **SoftwareInstallation**

Indicates whether to install the deployed software outside of maintenance windows. A maintenance window is a specified period of time used for computer maintenance and updates. If this value is $True, the Configuration Manager installs software according to schedule, even if the schedule falls outside a maintenance window. If this value is $False, Configuration Manager does not install deployed software outside any windows, but waits for a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **StandardProgramName**

Specifies a standard program name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SystemRestart**

Indicates whether a system restarts outside a maintenance window. A maintenance window is a specified period of time used for computer maintenance and updates. If this value is $True, any required restart takes place without regard to maintenance windows. If this value is $False, the computer does not restart outside a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseMeteredNetwork**

{{ Fill UseMeteredNetwork Description }}






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseRecurrencePattern**

Indicates whether to use a recurrence pattern.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseUtc**

Indicates whether to use Coordinated Universal Time (UTC), also known as Greenwich Mean Time. If this value is $True, Configuration Manager uses UTC for this deployment. If this value is $False, Configuration Manager uses local time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseUtcForAvailableSchedule**

Indicates whether to use UTC for available schedule. If this value is $True, Configuration Manager uses UTC. If this value is $False, Configuration Manager uses local time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseUtcForExpireSchedule**

Indicates whether to use UTC for expire schedule. If this value is $True, Configuration Manager uses UTC. If this value is $False, Configuration Manager uses local time.






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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMPackageDeployment [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DisableWildcardHandling] [-EnableExpireSchedule <Boolean>] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgramName <String> [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMPackageDeployment [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DisableWildcardHandling] [-EnableExpireSchedule <Boolean>] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] -PackageName <String> [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgramName <String> [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMPackageDeployment [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DisableWildcardHandling] [-EnableExpireSchedule <Boolean>] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] -PackageId <String> [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgramName <String> [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeploymentStartDateTime <DateTime>] -DeviceProgramName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageName <String> [-PassThru] [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseRecurrencePattern <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeploymentStartDateTime <DateTime>] -DeviceProgramName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageId <String> [-PassThru] [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseRecurrencePattern <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeploymentStartDateTime <DateTime>] -DeviceProgramName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseRecurrencePattern <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
