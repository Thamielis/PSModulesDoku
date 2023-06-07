Start-CMPackageDeployment
-------------------------




### Synopsis
(Deprecated) Starts deployment of a software package to a Configuration Manager collection.



---


### Description

> [!IMPORTANT] > This cmdlet is deprecated. Use New-CMPackageDeployment (New-CMPackageDeployment.md)instead.



The Start-CMPackageDeployment cmdlet starts deployment of a specified software package to computers that belong to a Configuration Manager collection. You can choose when the package becomes available and when the package deployment expires. You can specify whether Configuration Manager deploys the package only once or repeatedly and what happens when installation fails for a computer.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMPackageDeployment](New-CMPackageDeployment)



* [Get-CMPackageDeployment](Get-CMPackageDeployment)



* [Get-CMPackageDeploymentStatus](Get-CMPackageDeploymentStatus)



* [Set-CMPackageDeployment](Set-CMPackageDeployment)



* [Remove-CMPackageDeployment](Remove-CMPackageDeployment)



* [Get-CMPackage](Get-CMPackage)





---


### Examples
#### Example 1: Start a recurring deployment
```PowerShell
PS XYZ:\> Start-CMPackageDeployment -CollectionName "All Systems" -DeviceProgramName "DPM" -PackageName "User State Migration Tool for Windows 8" -Comment "DPM for all systems." -DeploymentStartDay 2012/10/26 -DeploymentStartTime 12:12 -RecurUnit Days -RecurValue 7 -Rerun $True -UseMeteredNetwork $True -UseUtc $True
```
This command starts deployment for a named package to the collection named All Systems for the device program named DPM. The command specifies a start day and start time. The command includes a descriptive comment. The Rerun parameter has a value of $True and the command specifies a recur value of seven and a recur unit of Days, so deployment reruns every seven days. The deployment uses metered network. The deployment uses UTC time.
#### Example 2: Start a recurring deployment for an available package
```PowerShell
PS XYZ:\> Start-CMPackageDeployment -CollectionName "Western Computers" -DeviceProgramName "DPM" -PackageName "User State Migration Tool for Windows 8" -Comment "Deployment for Western office." -DeployPurpose Available -Rerun $True -UseUtc $True
```
This command starts deployment for a named package to the collection named Western Computers for the device program named DPM. The command includes a descriptive comment. The command specifies Available as the DeployPurpose , therefor users can decide whether to install this software. The Rerun parameter has a value of $True. The deployment uses UTC time.
#### Example 3: Start a deployment for a standard program
```PowerShell
PS XYZ:\> Start-CMPackageDeployment -CollectionName "All Systems" -PackageName "User State Migration Tool for Windows 8" -StandardProgramName "SPM" AllowSharedContent $False
```
This command starts a deployment of a package named User State Migration Tool for Windows 8 to the collection named All Systems for the standard program named SPM. The command does not allow computers to use shared content.


---


### Parameters
#### **AllowSharedContent**

Indicates whether clients use shared content. If this value is $True, clients attempt to download content from other clients that downloaded that content. If this value is $False, clients do not attempt to download from other clients.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CollectionName**

Specifies the ID of a device or user collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **DeploymentAvailableDay**

Obsolete. Use DeploymentAvailableDateTime .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentAvailableTime**

Obsolete. Use DeploymentAvailableDateTime instead.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentExpireDateTime**

Specifies, as a DateTime object, the date and time that the deployment expires. To obtain a DateTime object, use the Get-Date cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentExpireDay**

Obsolete. Use DeploymentExpireDateTime instead.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentExpireTime**

Obsolete. Use DeploymentExpireDateTime .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentStartDateTime**

Specifies, as a DateTime object, the date and time that the deployment starts. To obtain a DateTime object, use the Get-Date cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentStartDay**

Obsolete. Use DeploymentStartDateTime .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentStartTime**

Obsolete. Use DeploymentStartDateTime .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeployPurpose**

Specifies the purpose for the deployment. The acceptable values for this parameter are:


* Available


* Required



Valid Values:

* Available
* Required






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[DeployPurposeType]`|false   |named   |False        |



#### **DeviceProgram**

Specifies a device program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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



#### **Package**

Specifies a package object. To obtain a package object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



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



#### **Program**

Specifies a program.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **ProgramName**

Specifies the name of a program.






|Type      |Required|Position|PipelineInput|Aliases                                  |
|----------|--------|--------|-------------|-----------------------------------------|
|`[String]`|true    |named   |False        |StandardProgramName<br/>DeviceProgramName|



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
* AlwaysRetunProgram
* AlwaysRerunProgram
* RerunIfFailedPreviousAttempt
* RerunIfSucceededOnPreviousAttempt






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[RerunBehaviorType]`|false   |named   |False        |



#### **RunFromSoftwareCenter**

Indicates whether to run from Software Center.






|Type       |Required|Position|PipelineInput|Aliases                   |
|-----------|--------|--------|-------------|--------------------------|
|`[Boolean]`|false   |named   |False        |AllowUsersRunIndependently|



#### **Schedule**

Specifies a schedule object for the deployment.






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






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[ScheduleEventType]`|false   |named   |False        |



#### **SendWakeupPacket**

Indicates whether to send a wake up packet to computers before the deployment begins. If this value is $True, Configuration Manager wakes a computer from sleep. If this value is $False, it does not wake computers from sleep. For computers to wake, you must first configure Wake On LAN.






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



#### **StandardProgram**

Indicates that the program type in the deployment package is standard program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SystemRestart**

Indicates whether a system restarts outside a maintenance window. A maintenance window is a specified period of time used for computer maintenance and updates. If this value is $True, any required restart takes place without regard to maintenance windows. If this value is $False, the computer does not restart outside a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseMeteredNetwork**

Indicates whether to allow clients to download content over a metered Internet connection after the deadline, which may incur additional expense.






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
Start-CMPackageDeployment [-Package] <IResultObject> [-AllowSharedContent <Boolean>] -CollectionName <String> [-Comment <String>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentExpireDay <DateTime>] [-DeploymentExpireTime <DateTime>] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] -ProgramName <String> [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRetunProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgram [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMPackageDeployment [-AllowSharedContent <Boolean>] -CollectionName <String> [-Comment <String>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentExpireDay <DateTime>] [-DeploymentExpireTime <DateTime>] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] -PackageName <String> [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] -ProgramName <String> [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRetunProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgram [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMPackageDeployment [-AllowSharedContent <Boolean>] -CollectionName <String> [-Comment <String>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentExpireDay <DateTime>] [-DeploymentExpireTime <DateTime>] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] -PackageId <String> [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] -ProgramName <String> [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRetunProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgram [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMPackageDeployment [-Program] <IResultObject> [-AllowSharedContent <Boolean>] -CollectionName <String> [-Comment <String>] [-DeploymentAvailableDateTime <DateTime>] [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentExpireDay <DateTime>] [-DeploymentExpireTime <DateTime>] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRetunProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgram [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMPackageDeployment -CollectionName <String> [-Comment <String>] [-DeploymentStartDateTime <DateTime>] [-DeploymentStartDay <DateTime>] [-DeploymentStartTime <DateTime>] [-DeployPurpose {Available | Required}] -DeviceProgram [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageName <String> [-PassThru] -ProgramName <String> [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMPackageDeployment -CollectionName <String> [-Comment <String>] [-DeploymentStartDateTime <DateTime>] [-DeploymentStartDay <DateTime>] [-DeploymentStartTime <DateTime>] [-DeployPurpose {Available | Required}] -DeviceProgram [-DisableWildcardHandling] [-ForceWildcardHandling] -PackageId <String> [-PassThru] -ProgramName <String> [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMPackageDeployment [-Package] <IResultObject> -CollectionName <String> [-Comment <String>] [-DeploymentStartDateTime <DateTime>] [-DeploymentStartDay <DateTime>] [-DeploymentStartTime <DateTime>] [-DeployPurpose {Available | Required}] -DeviceProgram [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -ProgramName <String> [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMPackageDeployment [-Program] <IResultObject> -CollectionName <String> [-Comment <String>] [-DeploymentStartDateTime <DateTime>] [-DeploymentStartDay <DateTime>] [-DeploymentStartTime <DateTime>] [-DeployPurpose {Available | Required}] -DeviceProgram [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-SendWakeupPacket <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
