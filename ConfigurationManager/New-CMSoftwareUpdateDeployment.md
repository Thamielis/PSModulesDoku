New-CMSoftwareUpdateDeployment
------------------------------




### Synopsis
Create a software update deployment.



---


### Description

Use this cmdlet to deploy software updates to a target collection.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMSoftwareUpdateDeployment](Set-CMSoftwareUpdateDeployment)





---


### Examples
#### Example 1
```PowerShell
New-CMSoftwareUpdateDeployment -DeploymentName "updates deployment" -SoftwareUpdateGroupName "software update group" -CollectionName "Desktop clients for SUM" -Description "a more detailed description of this deployment" -DeploymentType Required -VerbosityLevel AllMessages -AvailableDateTime "2020/08/25 02:00AM" -DeadlineDateTime "2020/08/26 02:00AM" -UserNotification DisplaySoftwareCenterOnly -SoftwareInstallation $True  -AllowRestart $True  -RestartServer $False -RestartWorkstation $False -PersistOnWriteFilterDevice $True -RequirePostRebootFullScan $True -ProtectedType RemoteDistributionPoint
```



---


### Parameters
#### **AcceptEula**

Some software updates include license terms. When you deploy software updates, the license terms aren't displayed. Add this parameter to automatically deploy all software updates regardless of an associated license term.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **AllowRestart**

When the installation deadline is reached, set this parameter to `$true` to allow system restart if necessary outside the maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AvailableDateTime**

Specify when the software updates are available.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **Collection**

Specifies a collection object in Configuration Manager the deployment will target. Get this object with the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify the collection ID as the target for this software update deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the collection name as the target for this software update deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specify an optional description for the software update deployment.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |Description|



#### **DeadlineDateTime**

Specify an installation deadline for required software updates. When the deadline is reached, the client installs required software updates on the device, and restarts the device if necessary.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentName**

Specify a name for the software update deployment.






|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|false   |named   |False        |UpdateGroupDeploymentName|



#### **DeploymentType**

Specify if this deployment is available for users to install or if it's a required installation at the specified deadline schedule.



Valid Values:

* Required
* Available






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[DeploymentType]`|false   |named   |False        |



#### **DeployWithNoPackage**

Set this parameter to `$true` to not use a deployment package. Clients download software update content from peers or the Microsoft cloud.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableOperationsManagerAlert**

Indicates whether to disable Operations Manager alerts during software updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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

Add this parameter to distribute the software update content when you create this deployment. Clients can't install the software updates until you distribute content to distribution points that the clients can access.






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



#### **DownloadFromMicrosoftUpdate**

If software update content isn't available on a distribution point in current, neighbor, or site boundary groups, download content from Microsoft Update.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateOperationsManagerAlert**

Indicates whether to generate Operations Manager alerts when a software installation fails.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **GenerateSuccessAlert**

If compliance of the deployment is below a specified threshold, the deployment generates an alert in the Configuration Manager console. The default threshold is 95 percent. To change the threshold, use the PercentSuccess parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**

Specify a software update object to deploy.






|Type             |Required|Position|PipelineInput |Aliases                               |
|-----------------|--------|--------|--------------|--------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SoftwareUpdate<br/>SoftwareUpdateGroup|



#### **PercentSuccess**

If you set -GenerateSuccessAlert to `$true`, use this parameter to specify the percentage compliance threshold at which the site generates a Configuration Manager console alert. If not specified, the site generates an alert if the deployment doesn't achieve 95 percent compliance by the specified deadline.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PersistOnWriteFilterDevice**

Indicates whether to install a software update on the temporary overlay and commit changes later, or commit the changes at an installation deadline or a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ProtectedType**

Specify whether clients can use a distribution point from a neighbor boundary group or the default site boundary group.



Valid Values:

* NoInstall
* RemoteDistributionPoint






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[ProtectedType]`|false   |named   |False        |



#### **RequirePostRebootFullScan**

This parameter controls the following console option: Software updates deployment re-evaluation behavior upon restart . If you set this option to `$true`, after clients restart when they install updates from this deployment, they then run a full update deployment evaluation cycle.






|Type       |Required|Position|PipelineInput|Aliases                  |
|-----------|--------|--------|-------------|-------------------------|
|`[Boolean]`|false   |named   |False        |RunEvaluationAfterRestart|



#### **RestartServer**

Indicates whether to allow a server to restart following a software update.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RestartWorkstation**

Indicates whether to allow a workstation to restart following a software update.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SavedPackageId**








|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|false   |named   |False        |SavedDeploymentPackageId|



#### **SendWakeupPacket**

Indicates whether to send a wake-up packet to computers before the deployment begins.


* `$True`: Configuration Manager wakes a computer from sleep.


* `$False`: It doesn't wake computers from sleep.




For computers to wake, first configure Wake On LAN.







|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SoftDeadlineEnabled**

Use this parameter to set the following option on the Deployment Schedule page of the ADR deployment settings: Delay enforcement of this deployment according to user preferences, up to the grace period defined in client settings .






|Type       |Required|Position|PipelineInput|Aliases                           |
|-----------|--------|--------|-------------|----------------------------------|
|`[Boolean]`|false   |named   |False        |DelayEnforcementAndUpToGracePeriod|



#### **SoftwareInstallation**

When the installation deadline is reached, set this parameter to `$true` to allow software update installation outside the maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SoftwareUpdateGroupId**

Specify the ID of a software update group to deploy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateGroupName**

Specify the name of a software update group to deploy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateId**

Specify the ID of a software update to deploy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateName**

Specify the name of a software update to deploy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TimeBasedOn**

Specify that clients use either local or UTC time to determine the availability of the deployment. UTC time makes the software update available at the same time for all computers.



Valid Values:

* LocalTime
* Utc






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[TimeType]`|false   |named   |False        |



#### **TimeUnit**

Specify the type of value of the -TimeValue parameter.



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **TimeValue**

Specify an integer value for the time. Use the -TimeUnit parameter to determine the type of time for this value.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UnprotectedType**

When software updates aren't available on any distribution points in current or neighbor boundary group, specify whether clients can download and install software updates from distribution points in the site default boundary group.



Valid Values:

* NoInstall
* UnprotectedDistributionPoint






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[UnprotectedType]`|false   |named   |False        |



#### **UseBranchCache**

Indicates whether to use Windows BranchCache to download software update content.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseMeteredNetwork**

Indicates whether to allow clients to use a metered network to download updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UserNotification**

Specify a user notification experience.


* `DisplayAll`: Display in Software Center and show all notifications


* `DisplaySoftwareCenterOnly`: Display in Software Center and only show notifications for computer restarts


* `HideAll`: Hide in Software Center and all notifications



Valid Values:

* DisplayAll
* DisplaySoftwareCenterOnly
* HideAll






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[UserNotificationType]`|false   |named   |False        |



#### **VerbosityLevel**

Specify the state message detail level returned by clients for this software update deployment.



Valid Values:

* AllMessages
* OnlySuccessAndErrorMessages
* OnlyErrorMessages






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[VerbosityLevelType]`|false   |named   |False        |



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
New-CMSoftwareUpdateDeployment [-AcceptEula] [-AllowRestart <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-DeployWithNoPackage <Boolean>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-DownloadFromMicrosoftUpdate <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] -InputObject <IResultObject> [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RequirePostRebootFullScan <Boolean>] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SavedPackageId <String>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SoftwareInstallation <Boolean>] [-TimeBasedOn {LocalTime | Utc}] [-TimeUnit {Hours | Days | Weeks | Months}] [-TimeValue <Int32>] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateDeployment [-AcceptEula] [-AllowRestart <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-DeployWithNoPackage <Boolean>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-DownloadFromMicrosoftUpdate <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RequirePostRebootFullScan <Boolean>] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SavedPackageId <String>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateGroupId <String> [-TimeBasedOn {LocalTime | Utc}] [-TimeUnit {Hours | Days | Weeks | Months}] [-TimeValue <Int32>] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateDeployment [-AcceptEula] [-AllowRestart <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-DeployWithNoPackage <Boolean>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-DownloadFromMicrosoftUpdate <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RequirePostRebootFullScan <Boolean>] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SavedPackageId <String>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateGroupName <String> [-TimeBasedOn {LocalTime | Utc}] [-TimeUnit {Hours | Days | Weeks | Months}] [-TimeValue <Int32>] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateDeployment [-AcceptEula] [-AllowRestart <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-DeployWithNoPackage <Boolean>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-DownloadFromMicrosoftUpdate <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RequirePostRebootFullScan <Boolean>] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SavedPackageId <String>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateId <String> [-TimeBasedOn {LocalTime | Utc}] [-TimeUnit {Hours | Days | Weeks | Months}] [-TimeValue <Int32>] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSoftwareUpdateDeployment [-AcceptEula] [-AllowRestart <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-DeployWithNoPackage <Boolean>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-DownloadFromMicrosoftUpdate <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RequirePostRebootFullScan <Boolean>] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SavedPackageId <String>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateName <String> [-TimeBasedOn {LocalTime | Utc}] [-TimeUnit {Hours | Days | Weeks | Months}] [-TimeValue <Int32>] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
