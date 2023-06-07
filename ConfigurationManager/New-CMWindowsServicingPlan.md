New-CMWindowsServicingPlan
--------------------------




### Synopsis
Creates a Windows 10 servicing plan.



---


### Description

The New-CMWindowsServicingPlan cmdlet creates a Windows 10 servicing plan.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMSoftwareUpdateDeploymentPackage](Get-CMSoftwareUpdateDeploymentPackage)



* [Get-CMWindowsServicingPlan](Get-CMWindowsServicingPlan)





---


### Examples
#### Example 1: Create a servicing plan by collection ID
```PowerShell
PS XYZ:\> $Lang = ("Japanese", "English", "French")
PS XYZ:\> $Required = (">=1", "<=100")
PS XYZ:\> $Title = ("Title1", "Title2", "Title3")
PS XYZ:\> New-CMWindowsServicingPlan -Name "Test01" -CollectionId MP40001A -Description "Servicing Plan description01" -SendWakeupPacket $False -VerboseLevel AllMessages -Language $Lang -Required $Required -Title $Title -RunType DoNotRunThisRuleAutomatically -UseUtc $True -AvailableImmediately $True -DeadlineImmediately $False -UserNotification DisplayAll -AllowSoftwareInstallationOutsideMaintenanceWindow $True -AllowRestart $True -SuppressRestartServer $True -SuppressRestartWorkstation $True -DeploymentPackage (Get-CMSoftwareUpdateDeploymentPackage -Name "SUDP01")
```
The first command creates a list of languages and stores the list in the $Lang variable.


The second command creates a list of search strings and stores the list in the $Required variable. This search string will find software updates required on at least one computer and maximum of 100 computers.


The third command creates a list of software update titles and stores the list in the $Title variable.


The last command gets the software update deployment package named SUDP01 and then creates a Windows servicing plan named Test for the target collection with the ID MP40001A. The command adds the upgrade filter languages stored in $Lang, the required filter stored in $Required, and the software update title filter stored in $Title.
#### Example 2: Create a servicing plan by collection name
```PowerShell
PS XYZ:\> $LangSelect = ("Japanese", "English", "French", "German")
PS XYZ:\> New-CMWindowsServicingPlan -Name "Test02" -CollectionName "ColName02" -DeploymentPackage (Get-CMSoftwareUpdateDeploymentPackage -Name "SUP02") -WriteFilterHandling $True -GenerateSuccessAlert $True -SuccessPercentage $True -AlertTime 10 -AlertTimeUnit Days -DisableOperationManager $True -GenerateOperationManagerAlert $True -NoInstallOnRemote $True -NoInstallOnUnprotected $True -UseBranchCache $True -DownloadFromMicrosoftUpdate $True -AllowUseMeteredNetwork $True -DownloadFromInternet $True -Location "\\TestSevr\WSUSTemp" -DeploymentRing Cbb -UpdateDeploymentWaitDay 20 -LanguageSelection $LangSelect
```
The first command creates a list of language selection languages and stores the list in the $LangSelect variable.


The second command gets the software update deployment package named SUP02 and then creates a Windows servicing plan named Test02 for the target collection named ColName02. The command adds the language select languages stored in $LangSelect.


---


### Parameters
#### **AlertTime**

Specifies an integer offset from an update deployment deadline. The rule uses this value to specify when the rule generates alerts. Specify a time unit by using the AlertTimeUnit parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **AlertTimeUnit**

Specifies a unit of time for the AlertTime parameter. Valid values are:


* Hours


* Days


* Weeks


* Months



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **AllowRestart**

Indicates whether a system restart is allowed to be performed outside of any defined maintenance windows when the installation deadline is reached.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowSoftwareInstallationOutsideMaintenanceWindow**

Indicates whether software installation is allowed to be performed outside of any defined maintenance windows when the installation deadline is reached.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowUseMeteredNetwork**

Indicates whether to allow clients to download content over a metered Internet connection after the deadline, which may incur additional expense.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AvailableImmediately**

Indicates whether software updates are available to install as soon as possible after the rule is run.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AvailableTime**

Specify when software updates are available.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **AvailableTimeUnit**

Specifies the time unit type for the software available time. Valid values are:


* Hours


* Days


* Weeks


* Months



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **Collection**

Specifies the target device collection object to be used for the servicing plan. To obtain a device collection object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **CollectionId**

Specifies the ID of the target device collection to be used for the servicing plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specifies the name of the target device collection to be used for the servicing plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeadlineImmediately**

Indicates whether required software updates are installed as soon as possible when the deadline is reached.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DeadlineTime**

Specifies the number of time units for the deadline.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DeadlineTimeUnit**

Specifies the time unit type for the deadline. Valid values are:


* Hours


* Days


* Weeks


* Months



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **DeploymentPackage**

Specifies a software update deployment package. To obtain a software update deployment package, use the Get-CMSoftwareUpdateDeploymentPackage (Get-CMSoftwareUpdateDeploymentPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases    |
|-----------------|--------|--------|-------------|-----------|
|`[IResultObject]`|false   |named   |False        |InputObject|



#### **DeploymentRing**

Specifies the Windows readiness state to which the servicing plan should apply. Valid values are:


* CB


* Release


* BusinessMainstream


* Cbb


* Ltsb



Valid Values:

* CB
* CB
* BusinessMainstream
* BusinessMainstream
* Ltsb






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[DeploymentRing]`|false   |named   |False        |



#### **Description**

Specifies a description for the servicing plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableOperationManager**

Indicates whether to disable System Center Operations Manager alerts during software updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DownloadFromInternet**

Indicates whether to download software updates from the Internet.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DownloadFromMicrosoftUpdate**

Indicates whether computers download content from Microsoft Update if the software updates are unavailable on a preferred distribution point or remote distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Enable**

Indicates whether the servicing plan is enabled.






|Type       |Required|Position|PipelineInput|Aliases                     |
|-----------|--------|--------|-------------|----------------------------|
|`[Boolean]`|false   |named   |False        |Enabled<br/>EnableDeployment|



#### **GenerateOperationManagerAlert**

Indicates whether to generate Operations Manager alerts during a software update.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **GenerateSuccessAlert**

Indicates whether to generate an alert for successful deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Language**

Specifies an array of languages used to filter software upgrades that will be added to the service plan.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **LanguageSelection**

Specifies an array of languages, as strings. Computers download software updates available in the specified languages, in addition to non-language-specific updates.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **Location**

Specifies a network location to where the downloaded updates are located.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specifies a name for the servicing plan. The name must be unique, help to describe the objective of the rule, and identify it from others in the Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NoInstallOnRemote**

Indicates whether to allow installation of updates on remote systems. If you specify a value of $True, if the client is within a slow or unreliable network boundary, or when the client uses a fallback source location for content, then Configuration Manager does not install software updates. If you specify a value of $False, installation proceeds.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **NoInstallOnUnprotected**

Indicates whether to allow installation of updates on unprotected systems. If you specify a value of $True, if software updates are not available on any preferred distribution points, Configuration Manager does not download and install software updates. If you specify a value of $False, installation proceeds.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Required**

Specifies an array of search strings used to filter software upgrades that will be added to the service plan.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **RunType**

Specifies the mode in which an update runs. Valid values are:


* DoNotRunThisRuleAutomatically


* RunTheRuleAfterAnySoftwareUpdatePointSynchronization


* RunTheRuleOnSchedule



Valid Values:

* DoNotRunThisRuleAutomatically
* RunTheRuleAfterAnySoftwareUpdatePointSynchronization
* RunTheRuleOnSchedule






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[RunType]`|false   |named   |False        |



#### **Schedule**

Specifies the deadline time (from deployment available time). To create a schedule, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **SendWakeupPacket**

Indicates whether to send a wake-up packet to computers before the deployment begins. If this value is $True, Configuration Manager wakes a computer from sleep. If this value is $False, it does not wake computers from sleep. For computers to wake, you must first configure Wake On LAN.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SuccessPercentage**

Specifies a percentage for client compliance as an integer from 0 to 99. If compliance falls below this percentage, Configuration Manager produces optional alerts.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SuppressRestartServer**

Indicates whether a system restart is suppressed on servers when a software update requires a system restart to complete the installation process.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SuppressRestartWorkstation**

Indicates whether a system restart is suppressed on workstations when a software update requires a system restart to complete the installation process.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Title**

Specifies an array of search strings used to filter software update titles that will be added to the service plan.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **UpdateDeploymentWaitDay**

Specifies the number of days to wait after Microsoft has published a new upgrade before deploying in your environment.






|Type     |Required|Position|PipelineInput|Aliases                 |
|---------|--------|--------|-------------|------------------------|
|`[Int32]`|false   |named   |False        |UpdateDeploymentWaitDays|



#### **UseBranchCache**

Indicates whether to use a branch cache. If you specify a value of $True, clients share content on the same subnet.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UserNotification**

Specifies the notification behavior of the user visual experience. Valid values are:


* DisplayAll


* DisplaySoftwareCenterOnly


* HideAll



Valid Values:

* DisplayAll
* DisplaySoftwareCenterOnly
* HideAll






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[UserNotificationType]`|false   |named   |False        |



#### **UseUtc**

Indicates whether the schedule for this deployment is evaluated based upon Universal Coordinated Time (UTC).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **VerboseLevel**

Specifies the level of detail you want clients to report for deployments that this rule creates. Valid values are:


* AllMessages


* OnlyErrorMessages


* OnlySuccessAndErrorMessages



Valid Values:

* OnlyErrorMessages
* OnlySuccessAndErrorMessages
* AllMessages






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[VerboseLevelType]`|false   |named   |False        |



#### **WriteFilterHandling**

Indicates whether changes are committed at deadline or during a maintenance window (requires restarts). If set to $False, content is applied on the overlay and committed later.






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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMWindowsServicingPlan [-AlertTime <Int32>] [-AlertTimeUnit {Hours | Days | Weeks | Months}] [-AllowRestart <Boolean>] [-AllowSoftwareInstallationOutsideMaintenanceWindow <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-AvailableImmediately <Boolean>] [-AvailableTime <Int32>] [-AvailableTimeUnit {Hours | Days | Weeks | Months}] -Collection <IResultObject> [-DeadlineImmediately <Boolean>] [-DeadlineTime <Int32>] [-DeadlineTimeUnit {Hours | Days | Weeks | Months}] [-DeploymentPackage <IResultObject>] [-DeploymentRing {CB | Release | BusinessMainstream | Cbb | Ltsb}] [-Description <String>] [-DisableOperationManager <Boolean>] [-DownloadFromInternet <Boolean>] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-GenerateOperationManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-Language <String[]>] [-LanguageSelection <String[]>] [-Location <String>] -Name <String> [-NoInstallOnRemote <Boolean>] [-NoInstallOnUnprotected <Boolean>] [-Required <String[]>] [-RunType {DoNotRunThisRuleAutomatically | RunTheRuleAfterAnySoftwareUpdatePointSynchronization | RunTheRuleOnSchedule}] [-Schedule <IResultObject>] [-SendWakeupPacket <Boolean>] [-SuccessPercentage <Int32>] [-SuppressRestartServer <Boolean>] [-SuppressRestartWorkstation <Boolean>] [-Title <String[]>] [-UpdateDeploymentWaitDay <Int32>] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseUtc <Boolean>] [-VerboseLevel {OnlyErrorMessages | OnlySuccessAndErrorMessages | AllMessages}] [-WriteFilterHandling <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMWindowsServicingPlan [-AlertTime <Int32>] [-AlertTimeUnit {Hours | Days | Weeks | Months}] [-AllowRestart <Boolean>] [-AllowSoftwareInstallationOutsideMaintenanceWindow <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-AvailableImmediately <Boolean>] [-AvailableTime <Int32>] [-AvailableTimeUnit {Hours | Days | Weeks | Months}] -CollectionId <String> [-DeadlineImmediately <Boolean>] [-DeadlineTime <Int32>] [-DeadlineTimeUnit {Hours | Days | Weeks | Months}] [-DeploymentPackage <IResultObject>] [-DeploymentRing {CB | Release | BusinessMainstream | Cbb | Ltsb}] [-Description <String>] [-DisableOperationManager <Boolean>] [-DownloadFromInternet <Boolean>] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-GenerateOperationManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-Language <String[]>] [-LanguageSelection <String[]>] [-Location <String>] -Name <String> [-NoInstallOnRemote <Boolean>] [-NoInstallOnUnprotected <Boolean>] [-Required <String[]>] [-RunType {DoNotRunThisRuleAutomatically | RunTheRuleAfterAnySoftwareUpdatePointSynchronization | RunTheRuleOnSchedule}] [-Schedule <IResultObject>] [-SendWakeupPacket <Boolean>] [-SuccessPercentage <Int32>] [-SuppressRestartServer <Boolean>] [-SuppressRestartWorkstation <Boolean>] [-Title <String[]>] [-UpdateDeploymentWaitDay <Int32>] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseUtc <Boolean>] [-VerboseLevel {OnlyErrorMessages | OnlySuccessAndErrorMessages | AllMessages}] [-WriteFilterHandling <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMWindowsServicingPlan [-AlertTime <Int32>] [-AlertTimeUnit {Hours | Days | Weeks | Months}] [-AllowRestart <Boolean>] [-AllowSoftwareInstallationOutsideMaintenanceWindow <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-AvailableImmediately <Boolean>] [-AvailableTime <Int32>] [-AvailableTimeUnit {Hours | Days | Weeks | Months}] -CollectionName <String> [-DeadlineImmediately <Boolean>] [-DeadlineTime <Int32>] [-DeadlineTimeUnit {Hours | Days | Weeks | Months}] [-DeploymentPackage <IResultObject>] [-DeploymentRing {CB | Release | BusinessMainstream | Cbb | Ltsb}] [-Description <String>] [-DisableOperationManager <Boolean>] [-DownloadFromInternet <Boolean>] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-GenerateOperationManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-Language <String[]>] [-LanguageSelection <String[]>] [-Location <String>] -Name <String> [-NoInstallOnRemote <Boolean>] [-NoInstallOnUnprotected <Boolean>] [-Required <String[]>] [-RunType {DoNotRunThisRuleAutomatically | RunTheRuleAfterAnySoftwareUpdatePointSynchronization | RunTheRuleOnSchedule}] [-Schedule <IResultObject>] [-SendWakeupPacket <Boolean>] [-SuccessPercentage <Int32>] [-SuppressRestartServer <Boolean>] [-SuppressRestartWorkstation <Boolean>] [-Title <String[]>] [-UpdateDeploymentWaitDay <Int32>] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseUtc <Boolean>] [-VerboseLevel {OnlyErrorMessages | OnlySuccessAndErrorMessages | AllMessages}] [-WriteFilterHandling <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
