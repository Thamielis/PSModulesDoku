New-CMPackageDeployment
-----------------------




### Synopsis
Deploy a legacy package to a collection.



---


### Description

Use this cmdlet to deploy a package to resources in a collection. You can specify the collection by ID, name, or pass an object.



For other deployment settings that you can't configure with this cmdlet, use Set-CMPackageDeployment (Set-CMPackageDeployment.md).



For more information, see Packages and programs in Configuration Manager (/mem/configmgr/apps/deploy-use/packages-and-programs#deploy-packages-and-programs).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMPackageDeployment](Get-CMPackageDeployment)



* [Get-CMPackageDeploymentStatus](Get-CMPackageDeploymentStatus)



* [Set-CMPackageDeployment](Set-CMPackageDeployment)



* [Remove-CMPackageDeployment](Remove-CMPackageDeployment)



* [Get-CMPackage](Get-CMPackage)



* [Packages and programs in Configuration Manager](Packages and programs in Configuration Manager)





---


### Examples
#### Example 1: Deploy a package by ID
```PowerShell
$pkgId = "XYZ00001"
$collId = "XYZ0003F"
New-CMPackageDeployment -StandardProgram -PackageId $pkgId -ProgramName "ScanState" -CollectionID $collId -Comment "Use USMT to scan for data" -DeployPurpose Available
```

#### Example 2: Deploy a package as required with a deadline
```PowerShell
[datetime]$DeadlineTime = (Get-Date -Hour 20 -Minute 0 -Second 0).AddDays(10)

$NewScheduleDeadline = New-CMSchedule -Start $DeadlineTime -Nonrecurring

$pkgId = "XYZ00001"
$progName = "Run"
$collId = "XYZ0003F"

New-CMPackageDeployment -StandardProgram -PackageId $pkgId -ProgramName $progName -DeployPurpose Required -CollectionId $collId -FastNetworkOption DownloadContentFromDistributionPointAndRunLocally -SlowNetworkOption DownloadContentFromDistributionPointAndLocally -RerunBehavior RerunIfFailedPreviousAttempt -Schedule $NewScheduleDeadline
```



---


### Parameters
#### **AllowFallback**

Allow clients to use distribution points from the default site boundary group.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowSharedContent**

Allow clients to use distribution points from a neighbor boundary group.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AvailableDateTime**

Specify when this deployment is available .


Use -DeadlineDateTime to specify when the deployment expires , and -Schedule to specify the deployment assignment, or deadline .


To get a DateTime object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **Collection**

Specify a collection object as the target for this package deployment. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify a collection ID as the target for this package deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify a collection name as the target for this package deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specify an optional comment for this package deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeadlineDateTime**

Use this parameter to specify when the deployment expires .


Use -AvailableDateTime to specify when the deployment is available , and -Schedule to specify the deployment assignment, or deadline .


To get a DateTime object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeployPurpose**

Specify whether this deployment is available for users to install, or it's required to install at the deadline.



Valid Values:

* Available
* Required






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[DeployPurposeType]`|false   |named   |False        |



#### **DeviceProgram**

If the program for the package that you're deploying is a device-type program, specify this parameter.


Otherwise, use the StandardProgram parameter. The standard program type is for computers with the Configuration Manager client.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



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

Add this parameter to distribute the package content when you create this deployment. Clients can't install the package until you distribute content to distribution points that the clients can access.






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



#### **FastNetworkOption**

Specify the behavior when the client uses a distribution point from the current boundary group:


* Run program from distribution point


* Download content from distribution point and run locally




If you don't specify this parameter, it uses `DownloadContentFromDistributionPointAndRunLocally` by default. This option is more secure, because the client validates the content hash before it runs the program.




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

Specify a package object with the program to deploy. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **PackageId**

Specify the ID of the package with the program to deploy. This ID is a standard package ID, for example `XYZ007E3`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageName**

Specify the name of the package with the program to deploy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PersistOnWriteFilterDevice**

Configure how the client handles the write filter on Windows Embedded devices.


* `$true`: Commit changes at the deadline or during a maintenance window. A restart is required.


* `$false`: Apply content on the overlay and commit later.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Program**

Specify a program object to deploy. To get this object, use the Get-CMProgram (Get-CMProgram.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **ProgramName**

Specify the name of the program in the package to deploy.






|Type      |Required|Position|PipelineInput|Aliases                                  |
|----------|--------|--------|-------------|-----------------------------------------|
|`[String]`|true    |named   |False        |StandardProgramName<br/>DeviceProgramName|



#### **RecurUnit**

Specify a unit for a recurring deployment. Use the RecurValue parameter to specify the value for this unit.



Valid Values:

* Minutes
* Hours
* Days






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[RecurUnitType]`|false   |named   |False        |



#### **RecurValue**

Specify how often the deployment recurs.


This parameter depends on the unit type specified in the RecurUnit parameter:


* Hours : This value can be between `1` and `23` - Days : Between `1` and `31` - Minutes : Between `1` and `59`






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Rerun**

Indicate whether the deployment reruns:


* `$True`: The deployment runs again for clients as specified in the RerunBehavior parameter. This value is the default. - `$False`: The deployment doesn't run again.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RerunBehavior**

Specify whether the program reruns on a computer.


* `NeverRerunDeployedProgram`: Doesn't rerun, even if the deployment failed or files changed.


* `AlwaysRerunProgram`: Rerun as scheduled, even if the deployment succeeded. You can use this value for recurring deployments. This value is the default.


* `RerunIfFailedPreviousAttempt`: Rerun as scheduled, if the deployment failed on the previous attempt.


* `RerunIfSucceededOnPreviousAttempt`: Rerun only if the previous attempt succeeded.



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

Specify the event type that determines when the package deployment runs.



Valid Values:

* AsSoonAsPossible
* LogOn
* LogOff






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[ScheduleEventType]`|false   |named   |False        |



#### **SendWakeupPacket**

Indicates whether to send a wake-up packet to computers before the deployment begins. If this value is `$True`, Configuration Manager wakes a computer from sleep. If this value is `$False`, it doesn't wake computers from sleep. For computers to wake, first configure Wake On LAN.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SlowNetworkOption**

Specify the behavior when the client uses a distribution point from a neighbor boundary group or the default site boundary group:


* Do not run program


* Download content from distribution point and run locally


* Run program from distribution point




If you don't specify this parameter, it uses `DoNotRunProgram` by default.




Valid Values:

* DoNotRunProgram
* DownloadContentFromDistributionPointAndLocally
* RunProgramFromDistributionPoint






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[SlowNetworkOptionType]`|false   |named   |False        |



#### **SoftwareInstallation**

When the installation deadline is reached, set this parameter to `$true` to allow the package to install outside the maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **StandardProgram**

Use this parameter for standard program types. This type is for computers with the Configuration Manager client.


If the program for the package that you're deploying is a device-type program, use the DeviceProgram parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SystemRestart**

When the installation deadline is reached, set this parameter to `$true` to allow system restart if necessary outside the maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseMeteredNetwork**

Indicates whether to allow clients on a metered internet connection to download content after the installation deadline, which might incur more cost.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseUtc**

Indicates whether clients use Coordinated Universal Time (UTC) to determine the availability of a program. UTC time makes the deployment available at the same time for all computers. If you don't specify this parameter, or set it to `$false`, the client uses its local time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseUtcForAvailableSchedule**

Indicates whether clients use Coordinated Universal Time (UTC) to determine the availability of a program. UTC time makes the deployment available at the same time for all computers. If you don't specify this parameter, or set it to `$false`, the client uses its local time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseUtcForExpireSchedule**

Indicates whether clients use Coordinated Universal Time (UTC) to determine when a program is expired. UTC time expires the deployment at the same time for all computers. If you don't specify this parameter, or set it to `$false`, the client uses its local time.






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
New-CMPackageDeployment [-Package] <IResultObject> [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] [-PersistOnWriteFilterDevice <Boolean>] -ProgramName <String> [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgram [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackageDeployment [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] -PackageName <String> [-PersistOnWriteFilterDevice <Boolean>] -ProgramName <String> [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgram [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackageDeployment [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] -PackageId <String> [-PersistOnWriteFilterDevice <Boolean>] -ProgramName <String> [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgram [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackageDeployment [-Program] <IResultObject> [-AllowFallback <Boolean>] [-AllowSharedContent <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-FastNetworkOption {RunProgramFromDistributionPoint | DownloadContentFromDistributionPointAndRunLocally}] [-ForceWildcardHandling] [-PersistOnWriteFilterDevice <Boolean>] [-RerunBehavior {NeverRerunDeployedProgram | AlwaysRerunProgram | RerunIfFailedPreviousAttempt | RerunIfSucceededOnPreviousAttempt}] [-RunFromSoftwareCenter <Boolean>] [-Schedule <IResultObject[]>] [-ScheduleEvent {AsSoonAsPossible | LogOn | LogOff}] [-SendWakeupPacket <Boolean>] [-SlowNetworkOption {DoNotRunProgram | DownloadContentFromDistributionPointAndLocally | RunProgramFromDistributionPoint}] [-SoftwareInstallation <Boolean>] -StandardProgram [-SystemRestart <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtcForAvailableSchedule <Boolean>] [-UseUtcForExpireSchedule <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackageDeployment [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployPurpose {Available | Required}] -DeviceProgram [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-ForceWildcardHandling] -PackageName <String> -ProgramName <String> [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackageDeployment [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployPurpose {Available | Required}] -DeviceProgram [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-ForceWildcardHandling] -PackageId <String> -ProgramName <String> [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackageDeployment [-Package] <IResultObject> [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployPurpose {Available | Required}] -DeviceProgram [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-ForceWildcardHandling] -ProgramName <String> [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMPackageDeployment [-Program] <IResultObject> [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployPurpose {Available | Required}] -DeviceProgram [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-ForceWildcardHandling] [-RecurUnit {Minutes | Hours | Days}] [-RecurValue <Int32>] [-Rerun <Boolean>] [-SendWakeupPacket <Boolean>] [-UseMeteredNetwork <Boolean>] [-UseUtc <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
