Set-CMSoftwareUpdateDeployment
------------------------------




### Synopsis
Modify a software update deployment.



---


### Description

Use this cmdlet to modify a deployment of software updates in Configuration Manager.



For more information, see Deploy software updates in Configuration Manager (/mem/configmgr/sum/deploy-use/deploy-software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateDeployment](Get-CMSoftwareUpdateDeployment)



* [New-CMSoftwareUpdateDeployment](New-CMSoftwareUpdateDeployment)



* [Remove-CMSoftwareUpdateDeployment](Remove-CMSoftwareUpdateDeployment)



* [Deploy software updates in Configuration Manager](Deploy software updates in Configuration Manager)





---


### Examples
#### Example 1: Set a deployment with expiration time
```PowerShell
Set-CMSoftwareUpdateDeployment -SoftwareUpdateName "CT" -DeploymentName "Contoso-test1" -NewDeploymentName "Contoso-test5" -Description "Contoso-test5-deployment" -CollectionName "All Mobile Devices" -SendWakeUpPacket $False -VerbosityLevel OnlySuccessAndErrorMessages -TimeBasedOn LocalTime -DeploymentAvailableDay 2013/11/24 -DeploymentAvailableTime 13:26 -DeploymentExpireDay 2014/7/22 -DeploymentExpireTime 4:30 -UserNotification DisplayAll -SoftwareInstallation $False -AllowRestart $False -RestartServer $False -RestartWorkstation $False -PersistOnWriteFilterDevice $True -GenerateSuccessAlert $False -PercentSuccess 99  -DisableOperationsManagerAlert $False -GenerateOperationsManagerAlert $False -ProtectedType NoInstall -UnprotectedType UnprotectedDistributionPoint -UseBranchCache $True -DownloadFromMicrosoftUpdate $False -AllowUseMeteredNetwork $False
```

#### Example 2: Start a deployment without expiration time
```PowerShell
Set-CMSoftwareUpdateDeployment -SoftwareUpdateName "CT" -DeploymentName "Contoso-test2" -NewDeploymentName "Contoso-test6" -Description "Contoso-test6-deployment" -CollectionName "All Mobile Devices" -VerbosityLevel OnlyErrorMessages -TimeBasedOn LocalTime -DeploymentAvailableDay 2013/12/24 -DeploymentAvailableTime 3:56 -UserNotification DisplaySoftwareCenterOnly -PersistOnWriteFilterDevice $True -DisableOperationsManagerAlert $False -GenerateOperationsManagerAlert $False -ProtectedType NoInstall -UnprotectedType UnprotectedDistributionPoint -UseBranchCache $True -DownloadFromMicrosoftUpdate $False -AllowUseMeteredNetwork $False
```

#### Example 3: Start a deployment by software update group name and expiration time
```PowerShell
Set-CMSoftwareUpdateDeployment -SoftwareUpdateGroupName "CTG" -DeploymentName "Contoso-test3" -NewDeploymentName "Contoso-test7" -Description "Contoso-test7-deployment" -CollectionName "All Mobile Devices" -SendWakeUpPacket $False -VerbosityLevel OnlySuccessAndErrorMessages -TimeBasedOn LocalTime -DeploymentAvailableDay 2013/11/24 -DeploymentAvailableTime 13:26 -DeploymentExpireDay 2014/7/22 -DeploymentExpireTime 4:30 -UserNotification DisplayAll -SoftwareInstallation $False -AllowRestart $False -RestartServer $False -RestartWorkstation $False -PersistOnWriteFilterDevice $True -GenerateSuccessAlert $False -PercentSuccess 99  -DisableOperationsManagerAlert $False -GenerateOperationsManagerAlert $False -ProtectedType NoInstall -UnprotectedType UnprotectedDistributionPoint -UseBranchCache $True -DownloadFromMicrosoftUpdate $False -AllowUseMeteredNetwork $False
```

#### Example 4: Start a deployment by software update group name
```PowerShell
Set-CMSoftwareUpdateDeployment -SoftwareUpdateGroupName "CTG" -DeploymentName "Contoso-test4" -NewDeploymentName "Contoso-test8" -Description "Contoso-test8-deployment" -CollectionName "All Mobile Devices" -VerbosityLevel OnlyErrorMessages -TimeBasedOn LocalTime -DeploymentAvailableDay 2013/12/24 -DeploymentAvailableTime 3:56 -UserNotification DisplaySoftwareCenterOnly -PersistOnWriteFilterDevice $True -DisableOperationsManagerAlert $False -GenerateOperationsManagerAlert $False -ProtectedType NoInstall -UnprotectedType UnprotectedDistributionPoint -UseBranchCache $True -DownloadFromMicrosoftUpdate $False -AllowUseMeteredNetwork $False
```



---


### Parameters
#### **AlertDateTime**

If -GenerateSuccessAlert is `$true`, specify a time to generate the alert.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **AllowRestart**

Indicates whether to allow a restart following installation.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowUseMeteredNetwork**

Indicates whether to allow clients to use a metered network to download updates.






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



#### **DeploymentExpireDateTime**

Specify an expiration time for the deployment.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentName**

Specifies a name for a software update deployment in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentType**

Specify if this deployment is available for users to install or if it's a required installation at the specified deadline schedule.



Valid Values:

* Required
* Available






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[DeploymentType]`|false   |named   |False        |



#### **Description**

Specifies a description for a software update deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **DownloadFromMicrosoftUpdate**

Indicates whether clients download updates directly from Microsoft Update.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Enable**

Indicates whether this deployment is enabled.






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


> [!IMPORTANT] > This parameter currently only supports deployment of a single software update. It doesn't support deployment of software update groups.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**

Specify a software update object to deploy.






|Type             |Required|Position|PipelineInput |Aliases                                                                    |
|-----------------|--------|--------|--------------|---------------------------------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SoftwareUpdate<br/>DeploymentSummary<br/>SoftwareUpdateGroup<br/>Assignment|



#### **NewDeploymentName**

Rename this software update deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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

Indicate whether to suppress a server restart, if a restart is required to complete update installation.


* `$true`: Suppress the restart


* `$false`: Allow servers to restart






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RestartWorkstation**

Indicate whether to suppress a workstation restart, if a restart is required to complete update installation.


* `$true`: Suppress the restart


* `$false`: Allow servers to restart






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SendWakeupPacket**

Indicates whether to send a wake-up packet to computers before the deployment begins.


* `$True`: Configuration Manager wakes a computer from sleep.


* `$False`: It doesn't wake computers from sleep.




For computers to wake, first configure wake on LAN (/mem/configmgr/core/clients/deploy/configure-wake-on-lan).







|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SoftDeadlineEnabled**

Set this parameter to `$true` to delay enforcement of this deployment according to user preferences, up to the grace period defined in client settings.






|Type       |Required|Position|PipelineInput|Aliases                           |
|-----------|--------|--------|-------------|----------------------------------|
|`[Boolean]`|false   |named   |False        |DelayEnforcementAndUpToGracePeriod|



#### **SoftwareInstallation**

Indicates whether to allow the software update to install, even if the installation occurs outside of a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SoftwareUpdateGroupId**

Specifies an ID for a software update group. A software update group contains individual software updates.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateGroupName**

Specifies a name for a software update group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateId**

Specifies an ID for a software update in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SoftwareUpdateName**

Specifies a name for a software update in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TimeBasedOn**

Specifies that client computers use either local or UTC time to determine the availability of a program. UTC time makes the software update available at the same time for all computers.



Valid Values:

* LocalTime
* Utc






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[TimeType]`|false   |named   |False        |



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
Set-CMSoftwareUpdateDeployment [-AlertDateTime <DateTime>] [-AllowRestart <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-Description <String>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] -InputObject <IResultObject> [-NewDeploymentName <String>] [-PassThru] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RequirePostRebootFullScan <Boolean>] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SoftwareInstallation <Boolean>] [-TimeBasedOn {LocalTime | Utc}] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdateDeployment [-AlertDateTime <DateTime>] [-AllowRestart <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-Description <String>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-NewDeploymentName <String>] [-PassThru] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RequirePostRebootFullScan <Boolean>] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateGroupId <String> [-TimeBasedOn {LocalTime | Utc}] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdateDeployment [-AlertDateTime <DateTime>] [-AllowRestart <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-Description <String>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-NewDeploymentName <String>] [-PassThru] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RequirePostRebootFullScan <Boolean>] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateGroupName <String> [-TimeBasedOn {LocalTime | Utc}] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdateDeployment [-AlertDateTime <DateTime>] [-AllowRestart <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-Description <String>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-NewDeploymentName <String>] [-PassThru] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RequirePostRebootFullScan <Boolean>] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateId <String> [-TimeBasedOn {LocalTime | Utc}] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareUpdateDeployment [-AlertDateTime <DateTime>] [-AllowRestart <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentExpireDateTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-Description <String>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DownloadFromMicrosoftUpdate <Boolean>] [-Enable <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-NewDeploymentName <String>] [-PassThru] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RequirePostRebootFullScan <Boolean>] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateName <String> [-TimeBasedOn {LocalTime | Utc}] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
