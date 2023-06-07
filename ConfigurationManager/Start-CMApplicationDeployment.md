Start-CMApplicationDeployment
-----------------------------




### Synopsis
(Deprecated) Starts an application deployment in Configuration Manager.



---


### Description

> [!IMPORTANT] > This cmdlet is deprecated. Use New-CMApplicationDeployment (New-CMApplicationDeployment.md)instead.



The Start-CMApplicationDeployment cmdlet starts an application deployment.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMApplicationDeployment](Set-CMApplicationDeployment)





---


### Examples
#### Example 1: Start application deployment
```PowerShell
PS XYZ:\> Start-CMApplicationDeployment -CollectionName "All Users" -Name "7zip" -AvaliableDate 2012/10/1 -AvaliableTime 12:45 -Comment "test" -DeadlineDate 2013/10/23 -DeadlineTime 21:12 -DeployAction Uninstall -EnableMomAlert $True -FailParameterValue 40 -OverrideServiceWindow $True -PersistOnWriteFilterDevice $False -PostponeDate 2014/2/8 -PostponeTime 11:11 -PreDeploy $True -RaiseMomAlertsOnFailure $True -RebootOutsideServiceWindow $True -SendWakeUpPacket $True -SuccessParameterValue 30 -UseMeteredNetwork $True -UserNotification DisplaySoftwareCenterOnly
```
This command starts an application deployment named 7zip.


---


### Parameters
#### **ApprovalRequired**








|Type       |Required|Position|PipelineInput|Aliases            |
|-----------|--------|--------|-------------|-------------------|
|`[Boolean]`|false   |named   |False        |AppRequiresApproval|



#### **AvailableDate**








|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[DateTime]`|false   |named   |False        |AvailiableDate|



#### **AvailableDateTime**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **AvailableTime**








|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[DateTime]`|false   |named   |False        |AvailiableTime|



#### **CollectionName**

Specifies a target collection to deploy this application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Comment**

Specifies a comment for the application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeadlineDate**

Specifies a day by which to install an application. Autoinstall performs the installation if the application is not installed.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeadlineDateTime**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeadlineTime**

Specifies a time by which to install an application. Autoinstall performs the installation if the application is not installed.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DeployAction**

Specifies an action for a deployment. Valid values are:


* Install. Install the application.


* Uninstall. Uninstall the application.



Valid Values:

* Install
* Uninstall






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[DeployActionType]`|false   |named   |False        |



#### **DeployPurpose**

Specifies the purpose of the deployment.


Valid values are:


* Available. If the target collection is a device collection, the application is available in the software center. If the target collection is a user collection, the application is available in the catalog web site.


* Required. Installation occurs when the deadline passes.



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



#### **EnableMomAlert**

Indicates whether to enable Operations Manager maintenance mode.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **FailParameterValue**

Specifies a value that generates a deployment alert when exceeded.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateScomAlertOnFailure**








|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |RaiseMomAlertsOnFailure|



#### **Id**

Specifies an array of IDs.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies an application deployment object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies an array of names for the application deployment.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **OverrideServiceWindow**

Indicates whether an application installation occurs outside of a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PersistOnWriteFilterDevice**

Indicates whether to commit changes on a Windows Embedded device at deadline or during a maintenance window. Otherwise, changes are written on the overlay and committed later.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PostponeDate**

Specifies a date after which to create an alert.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **PostponeDateTime**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **PostponeTime**

Specifies a time after which to create an alert.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **PreDeploy**

Indicates whether to copy software to a device before installation. To use this parameter, set the DeployPurpose parameter to Required.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RebootOutsideServiceWindow**

Indicates whether a computer restarts outside a service window. A service window is a specified period of time used for computer maintenance and updates. If this value is $True, any required restart takes place without regard to service windows. If this value is $False, the computer does not restart outside a service window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SendWakeupPacket**

Indicates whether to send a wake up packet to computers before the deployment begins. If this value is $True, Configuration Manager wakes a computer from sleep. If this value is $False, it does not wake computers from sleep. For computers to wake, you must first configure Wake On LAN.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SuccessParameterValue**

Specifies a value that the threshold must exceed before an alert is created.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TimeBaseOn**

Specifies the time zone to use.


Valid values are:


* LocalTime. Use local time. - UTC. Use Coordinated Universal Time (UTC), also known as Greenwich Mean Time.



Valid Values:

* LocalTime
* Utc






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[TimeType]`|false   |named   |False        |



#### **UpdateSupersedence**

{{ Fill UpdateSupersedence Description }}






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UseMeteredNetwork**

Indicates whether clients can download content over metered Internet connections after the installation deadline. Clients may incur additional costs.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UserNotification**

Specifies user notification types.


Valid values are:


* DisplayAll. Display in Software Center and show all notifications.


* DisplaySoftwareCenterOnly. Display in Software Center and only show notifications for computer restarts.


* HideAll. Do not display in Software Center and do not show notifications.



Valid Values:

* DisplayAll
* DisplaySoftwareCenterOnly
* HideAll






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[UserNotificationType]`|false   |named   |False        |



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
Start-CMApplicationDeployment [-Id] <Int32> [-ApprovalRequired <Boolean>] [-AvailableDate <DateTime>] [-AvailableDateTime <DateTime>] [-AvailableTime <DateTime>] -CollectionName <String> [-Comment <String>] [-DeadlineDate <DateTime>] [-DeadlineDateTime <DateTime>] [-DeadlineTime <DateTime>] [-DeployAction {Install | Uninstall}] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-EnableMomAlert <Boolean>] [-FailParameterValue <Int32>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-OverrideServiceWindow <Boolean>] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-PostponeDate <DateTime>] [-PostponeDateTime <DateTime>] [-PostponeTime <DateTime>] [-PreDeploy <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-SendWakeupPacket <Boolean>] [-SuccessParameterValue <Int32>] [-TimeBaseOn {LocalTime | Utc}] [-UpdateSupersedence <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMApplicationDeployment [-InputObject] <IResultObject> [-ApprovalRequired <Boolean>] [-AvailableDate <DateTime>] [-AvailableDateTime <DateTime>] [-AvailableTime <DateTime>] -CollectionName <String> [-Comment <String>] [-DeadlineDate <DateTime>] [-DeadlineDateTime <DateTime>] [-DeadlineTime <DateTime>] [-DeployAction {Install | Uninstall}] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-EnableMomAlert <Boolean>] [-FailParameterValue <Int32>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-OverrideServiceWindow <Boolean>] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-PostponeDate <DateTime>] [-PostponeDateTime <DateTime>] [-PostponeTime <DateTime>] [-PreDeploy <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-SendWakeupPacket <Boolean>] [-SuccessParameterValue <Int32>] [-TimeBaseOn {LocalTime | Utc}] [-UpdateSupersedence <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMApplicationDeployment [-Name] <String> [-ApprovalRequired <Boolean>] [-AvailableDate <DateTime>] [-AvailableDateTime <DateTime>] [-AvailableTime <DateTime>] -CollectionName <String> [-Comment <String>] [-DeadlineDate <DateTime>] [-DeadlineDateTime <DateTime>] [-DeadlineTime <DateTime>] [-DeployAction {Install | Uninstall}] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-EnableMomAlert <Boolean>] [-FailParameterValue <Int32>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-OverrideServiceWindow <Boolean>] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-PostponeDate <DateTime>] [-PostponeDateTime <DateTime>] [-PostponeTime <DateTime>] [-PreDeploy <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-SendWakeupPacket <Boolean>] [-SuccessParameterValue <Int32>] [-TimeBaseOn {LocalTime | Utc}] [-UpdateSupersedence <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
