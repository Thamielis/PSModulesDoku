Start-CMSoftwareUpdateDeployment
--------------------------------




### Synopsis
(Deprecated) Initiates a software update deployment in Configuration Manager.



---


### Description

> [!IMPORTANT] > This cmdlet is deprecated. Use New-CMSoftwareUpdateDeployment (New-CMSoftwareUpdateDeployment.md)instead.



The Start-CMSoftwareUpdateDeployment cmdlet initiates a software update deployment.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate)



* [Get-CMSoftwareUpdateGroup](Get-CMSoftwareUpdateGroup)



* [Set-CMSoftwareUpdateDeployment](Set-CMSoftwareUpdateDeployment)





---


### Examples
#### Example 1: Start a required deployment by software update name
```PowerShell
PS XYZ:\> Start-CMSoftwareUpdateDeployment -SoftwareUpdateName "CT" -CollectionName "All Systems" -DeploymentName "Contoso-test" -Description "Contoso-test-deployment" -DeploymentType Required -SendWakeUpPacket $True -VerbosityLevel AllMessages -TimeBasedOn UTC -DeploymentAvailableDay 2012/10/24 -DeploymentAvailableTime 23:56 -DeploymentExpireDay 2013/10/21 -DeploymentExpireTime 11:20 -UserNotification HideAll -SoftwareInstallation $True -AllowRestart $True -RestartServer $True -RestartWorkstation $True -PersistOnWriteFilterDevice $False -GenerateSuccessAlert $True -PercentSuccess 90 -TimeValue 10 -TimeUnit Days -DisableOperationsManagerAlert $True -GenerateOperationsManagerAlert $True -ProtectedType RemoteDistributionPoint -UnprotectedType NoInstall -UseBranchCache $False -DownloadFromMicrosoftUpdate $True -AllowUseMeteredNetwork $True
```
This command starts a required software update deployment by using a software update name.
#### Example 2: Start an available deployment by software update name
```PowerShell
PS XYZ:\> Start-CMSoftwareUpdateDeployment -SoftwareUpdateName "CT" -CollectionName "All Systems" -DeploymentName "Contoso-test2" -Description "Contoso-test2-deployment" -DeploymentType Available -VerbosityLevel AllMessages -TimeBasedOn UTC -DeploymentAvailableDay 2012/10/24 -DeploymentAvailableTime 23:56 -UserNotification DisplayAll -PersistOnWriteFilterDevice $False -DisableOperationsManagerAlert $True -GenerateOperationsManagerAlert $True -ProtectedType RemoteDistributionPoint -UnprotectedType NoInstall -UseBranchCache $False -DownloadFromMicrosoftUpdate $True -AllowUseMeteredNetwork $True
```
This command starts an available software update deployment by using a software update name.
#### Example 3: Start a required deployment by software update group name
```PowerShell
PS XYZ:\> Start-CMSoftwareUpdateDeployment -SoftwareUpdateGroupName "CTG" -CollectionName "All Systems" -DeploymentName "Contoso-test3" -Description "Contoso-test3-deployment" -DeploymentType Required -SendWakeUpPacket $True -VerbosityLevel AllMessages -TimeBasedOn UTC -DeploymentAvailableDay 2012/10/24 -DeploymentAvailableTime 23:56 -DeploymentExpireDay 2013/10/21 -DeploymentExpireTime 11:20 -UserNotification HideAll -SoftwareInstallation $True -AllowRestart $True -RestartServer $True -RestartWorkstation $True -PersistOnWriteFilterDevice $False -GenerateSuccessAlert $True -PercentSuccess 90 -TimeValue 10 -TimeUnit Days -DisableOperationsManagerAlert $True -GenerateOperationsManagerAlert $True -ProtectedType RemoteDistributionPoint -UnprotectedType NoInstall -UseBranchCache $False -DownloadFromMicrosoftUpdate $True -AllowUseMeteredNetwork $True
```
This command starts a software update deployment by using a collection name and an input object.
#### Example 4: Start a deployment by software update group name
```PowerShell
PS XYZ:\> Start-CMSoftwareUpdateDeployment -SoftwareUpdateGroupName "CTG" -CollectionName "All Systems" -DeploymentName "Contoso-test4" -Description "Contoso-test4-deployment" -DeploymentType Available -VerbosityLevel AllMessages -TimeBasedOn UTC -DeploymentAvailableDay 2012/10/24 -DeploymentAvailableTime 23:56 -UserNotification DisplayAll -PersistOnWriteFilterDevice $False -DisableOperationsManagerAlert $True -GenerateOperationsManagerAlert $True -ProtectedType RemoteDistributionPoint -UnprotectedType NoInstall -UseBranchCache $False -DownloadFromMicrosoftUpdate $True -AllowUseMeteredNetwork $True
```
This command starts a software update deployment by using a software update group name.


---


### Parameters
#### **AcceptEula**

Some software updates include license terms. When you deploy software updates, the license terms aren't displayed. Add this parameter to automatically deploy all software updates regardless of an associated license term.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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



#### **CollectionName**

Specifies a name of a collection in Configuration Manager. A collection is a group of client computers.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeploymentAvailableDay**

Specifies a day, in MM/DD/YYYY format, when a software update deployment is available. By default, the update is available immediately.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentAvailableTime**

Specifies a time, in HH:MM format, when a software update deployment is available. By default, the update is available immediately.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeploymentName**

Specifies a name for a software update deployment in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentType**

Specifies a deployment type in Configuration Manager.



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

Indicates whether to disable System Center 2012 - Operations Manager alerts during software updates.






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



#### **EnforcementDeadline**








|Type        |Required|Position|PipelineInput|Aliases             |
|------------|--------|--------|-------------|--------------------|
|`[DateTime]`|false   |named   |False        |DeploymentExpireTime|



#### **EnforcementDeadlineDay**








|Type        |Required|Position|PipelineInput|Aliases            |
|------------|--------|--------|-------------|-------------------|
|`[DateTime]`|false   |named   |False        |DeploymentExpireDay|



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

Indicates whether to generate alerts when a software installation succeeds.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases                               |
|-----------------|--------|--------|--------------|--------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SoftwareUpdate<br/>SoftwareUpdateGroup|



#### **PercentSuccess**

Specifies a percent success.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PersistOnWriteFilterDevice**

Indicates whether to install a software update on the temporary overlay and commit changes later, or commit the changes at an installation deadline or a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ProtectedType**

Specifies a protected type.



Valid Values:

* NoInstall
* RemoteDistributionPoint






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[ProtectedType]`|false   |named   |False        |



#### **RestartServer**

Indicates whether to allow a server to restart following a software update. Setting this value to $True prevents the server from restarting. Setting this value to $False allows the server to restart.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RestartWorkstation**

Indicates whether to allow a workstation to restart following a software update. Setting this value to $True prevents the computer from restarting. Setting this value to $False allows the computer to restart.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SendWakeupPacket**

Indicates whether to send a wake up packet to computers before the deployment begins. If this value is $True, Configuration Manager wakes a computer from sleep. If this value is $False, it does not wake computers from sleep. For computers to wake, you must first configure Wake On LAN.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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



#### **TimeUnit**

Specifies the time unit in Configuration Manager. Valid values are:


* Days


* Hours


* Months


* Weeks



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **TimeValue**

Specifies a time value in the units specified in the TimeUnit parameter.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UnprotectedType**

Specifies an unprotected type.



Valid Values:

* NoInstall
* UnprotectedDistributionPoint






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[UnprotectedType]`|false   |named   |False        |



#### **UseBranchCache**

Indicates whether to use Branch Cache as a distribution point for updates.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UserNotification**

Specifies a user notification type.



Valid Values:

* DisplayAll
* DisplaySoftwareCenterOnly
* HideAll






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[UserNotificationType]`|false   |named   |False        |



#### **VerbosityLevel**

Specifies verbosity level. Valid values are:


* AllMessages


* OnlyErrorMessages


* OnlySuccessAndErrorMessages



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
Start-CMSoftwareUpdateDeployment [-AcceptEula] [-AllowRestart <Boolean>] [-AllowUseMeteredNetwork <Boolean>] -CollectionName <String> [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-Description <String>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DownloadFromMicrosoftUpdate <Boolean>] [-EnforcementDeadline <DateTime>] [-EnforcementDeadlineDay <DateTime>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] -InputObject <IResultObject> [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftwareInstallation <Boolean>] [-TimeBasedOn {LocalTime | Utc}] [-TimeUnit {Hours | Days | Weeks | Months}] [-TimeValue <Int32>] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMSoftwareUpdateDeployment [-AcceptEula] [-AllowRestart <Boolean>] [-AllowUseMeteredNetwork <Boolean>] -CollectionName <String> [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-Description <String>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DownloadFromMicrosoftUpdate <Boolean>] [-EnforcementDeadline <DateTime>] [-EnforcementDeadlineDay <DateTime>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateGroupId <String> [-TimeBasedOn {LocalTime | Utc}] [-TimeUnit {Hours | Days | Weeks | Months}] [-TimeValue <Int32>] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMSoftwareUpdateDeployment [-AcceptEula] [-AllowRestart <Boolean>] [-AllowUseMeteredNetwork <Boolean>] -CollectionName <String> [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-Description <String>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DownloadFromMicrosoftUpdate <Boolean>] [-EnforcementDeadline <DateTime>] [-EnforcementDeadlineDay <DateTime>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateGroupName <String> [-TimeBasedOn {LocalTime | Utc}] [-TimeUnit {Hours | Days | Weeks | Months}] [-TimeValue <Int32>] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMSoftwareUpdateDeployment [-AcceptEula] [-AllowRestart <Boolean>] [-AllowUseMeteredNetwork <Boolean>] -CollectionName <String> [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-Description <String>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DownloadFromMicrosoftUpdate <Boolean>] [-EnforcementDeadline <DateTime>] [-EnforcementDeadlineDay <DateTime>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateId <String> [-TimeBasedOn {LocalTime | Utc}] [-TimeUnit {Hours | Days | Weeks | Months}] [-TimeValue <Int32>] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMSoftwareUpdateDeployment [-AcceptEula] [-AllowRestart <Boolean>] [-AllowUseMeteredNetwork <Boolean>] -CollectionName <String> [-DeploymentAvailableDay <DateTime>] [-DeploymentAvailableTime <DateTime>] [-DeploymentName <String>] [-DeploymentType {Required | Available}] [-Description <String>] [-DisableOperationsManagerAlert <Boolean>] [-DisableWildcardHandling] [-DownloadFromMicrosoftUpdate <Boolean>] [-EnforcementDeadline <DateTime>] [-EnforcementDeadlineDay <DateTime>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-PercentSuccess <Int32>] [-PersistOnWriteFilterDevice <Boolean>] [-ProtectedType {NoInstall | RemoteDistributionPoint}] [-RestartServer <Boolean>] [-RestartWorkstation <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftwareInstallation <Boolean>] -SoftwareUpdateName <String> [-TimeBasedOn {LocalTime | Utc}] [-TimeUnit {Hours | Days | Weeks | Months}] [-TimeValue <Int32>] [-UnprotectedType {NoInstall | UnprotectedDistributionPoint}] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-VerbosityLevel {AllMessages | OnlySuccessAndErrorMessages | OnlyErrorMessages}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
