Set-CMApplicationDeployment
---------------------------




### Synopsis
Configure an application deployment



---


### Description

The Set-CMApplicationDeployment cmdlet modifies the properties of an application deployment in Configuration Manager. For more information, see Deploy applications with Configuration Manager (/mem/configmgr/apps/deploy-use/deploy-applications).



To specify an application deployment to modify, specify the collection name and the application. You can specify an application by name or ID. You can also use the Get-CMApplication (Get-CMApplication.md)cmdlet to get an application to modify.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplication](Get-CMApplication)



* [Get-CMApplicationDeployment](Get-CMApplicationDeployment)



* [New-CMApplicationDeployment](New-CMApplicationDeployment)



* [Remove-CMApplicationDeployment](Remove-CMApplicationDeployment)



* [Deploy applications with Configuration Manager](Deploy applications with Configuration Manager)





---


### Examples
#### Example 1: Modify availability and deadline for an application deployment
```PowerShell
Set-CMApplicationDeployment -ApplicationName "Track System 2011" -CollectionName "All Users" -AvailableDateTime (Get-Date) -DeadlineDateTime $(Get-Date).AddDays(30)
```
This command modifies an application deployment for an application named Track System 2011 for a collection named All Users . The command specifies the current date for when the application is available. It also configures the deployment deadline for 30 days in the future.


---


### Parameters
#### **AllowRepairApp**

Use this parameter to configure the repair application option when creating a deployment for an application.






|Type       |Required|Position|PipelineInput|Aliases                   |
|-----------|--------|--------|-------------|--------------------------|
|`[Boolean]`|false   |named   |False        |AllowUserRepairApplication|



#### **ApplicationId**

Specifies the ID of an application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ApplicationName**

Specifies the name of an application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **AutoCloseExecutable**

Starting in version 2107, set this parameter to `$true` to enable the application deployment setting for install behaviors. Then use the Add-CMDeploymentTypeInstallBehavior (Add-CMDeploymentTypeInstallBehavior.md)cmdlet to add an executable file to check isn't running for the install to succeed.


Set this parameter to `$false` to disable this option in the following situations:


* When you use the Remove-CMDeploymentTypeInstallBehavior (Remove-CMDeploymentTypeInstallBehavior.md)cmdlet to remove all executable files - You don't want the deployment to check for running executables.






|Type       |Required|Position|PipelineInput|Aliases                      |
|-----------|--------|--------|-------------|-----------------------------|
|`[Boolean]`|false   |named   |False        |AutoCloseExeOnInstallBehavior|



#### **AvailableDateTime**

Specify a DateTime object for when this deployment is available . To get this object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)built-in cmdlet.


Use DeadlineDateTime to specify the deployment assignment, or deadline .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **Collection**

Specify a collection object to which the application is deployed. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify the ID of the collection to which the application is deployed. For example, `"SMS00004"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the name of the collection to which the application is deployed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specifies an optional comment for the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CreateAlertBaseOnPercentFailure**

Indicates whether to create an alert for a percentage of the applications that fail to deploy. To specify the percentage value, use the FailParameterValue parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CreateAlertBaseOnPercentSuccess**

Indicates whether to create an alert for a percentage of the applications that deploy successfully. To specify the percentage value, use the SuccessParameterValue parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DeadlineDateTime**

Specify a DateTime object for when this deployment is assigned, also known as the deadline . To get this object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)built-in cmdlet.


Use -AvailableDateTime to specify when the deployment is available .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableMomAlert**

Set this parameter to `$true` to enable System Center Operations Manager maintenance mode for this deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSoftDeadline**

Set this parameter to `$true` to enable delayed enforcement.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **FailParameterValue**

Specifies the percentage of failed application installation that causes an alert. Specify an integer from 1 through 100. To enable this alert, set the CreatAlertBaseOnPercentFailure parameter to `$True`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an application deployment object to configure. To get this object, use the Get-CMApplicationDeployment (Get-CMApplicationDeployment.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                                         |
|-----------------|--------|--------|--------------|------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Application<br/>DeploymentSummary<br/>Assignment|



#### **OverrideServiceWindow**

Indicates whether the deployment takes place even if scheduled outside of a maintenance window. A maintenance window is a specified period of time used for computer maintenance and updates. If this value is `$True`, Configuration Manager deploys the application even if the scheduled time falls outside the maintenance window. If this value is `$False`, Configuration Manager doesn't deploy the application outside the window. It waits until it can deploy in an available window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PersistOnWriteFilterDevice**

Indicates whether to enable write filters for embedded devices. For a value of `$True`, the device commits changes during a maintenance window. This action requires a restart. For a value of `$False`, the device saves changes in an overlay and commits them later.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PostponeDateTime**

When you set CreateAlertBaseOnPercentSuccess to `$true`, use this parameter to specify a DateTime object. Configuration Manager creates a deployment alert when the threshold is lower than the SuccessParameterValue after this date.


To get this object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)built-in cmdlet.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **PreDeploy**

Indicates whether to pre-deploy the application to the primary device of the user.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RaiseMomAlertsOnFailure**

Indicates whether to create an Operations Manager alert if a client fails to install the application.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RebootOutsideServiceWindow**

Indicates whether a computer restarts outside a maintenance window. A maintenance window is a specified period of time used for computer maintenance and updates. If this value is `$True`, any required restart takes place without regard to maintenance windows. If this value is `$False`, the computer doesn't restart outside a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ReplaceToastNotificationWithDialog**

When required software is available on the client, set this parameter to `$true` to replace the default toast notifications with a dialog window. It's false by default. For more information, see Replace toast notifications with dialog window (/mem/configmgr/apps/plan-design/plan-for-software-center#bkmk_impact).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RequireApproval**

If you set this parameter to `$true`, an administrator must approve a request for this application on the device.






|Type       |Required|Position|PipelineInput|Aliases            |
|-----------|--------|--------|-------------|-------------------|
|`[Boolean]`|false   |named   |False        |AppRequiresApproval|



#### **SendWakeUpPacket**

Indicates whether to send a wake-up packet to computers before the deployment begins. If this value is `$True`, Configuration Manager attempts to wake a computer from sleep. If this value is `$False`, it doesn't wake computers from sleep. For computers to wake, you must first configure Wake On LAN.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SuccessParameterValue**

Specifies the percentage of successful application installation that causes an alert. Specify an integer from 0 through 99. To enable this alert, set the CreateAlertBaseOnPercentSuccess parameter as `$True`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TimeBaseOn**

Specifies which time zone to use:


* `LocalTime`: Use local time.


* `UTC`: Use Coordinated Universal Time (UTC).



Valid Values:

* LocalTime
* Utc






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[TimeType]`|false   |named   |False        |



#### **UseMeteredNetwork**

Indicates whether to allow clients to download content over a metered internet connection after the deadline, which may incur extra expense.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UserNotification**

Specifies the type of user notification.


* `DisplayAll`: Display in Software Center and show all notifications.


* `DisplaySoftwareCenterOnly`: Display in Software Center, and only show notifications of computer restarts.


* `HideAll`: Hide in Software Center and all notifications.



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
* IResultObject#SMS_ApplicationAssignment






---


### Notes
For more information on this return object and its properties, see SMS_ApplicationAssignment server WMI class (/mem/configmgr/develop/reference/apps/sms_applicationassignment-server-wmi-class).



---


### Syntax
```PowerShell
Set-CMApplicationDeployment [-AllowRepairApp <Boolean>] -ApplicationId <String> [-AutoCloseExecutable <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-CreateAlertBaseOnPercentFailure <Boolean>] [-CreateAlertBaseOnPercentSuccess <Boolean>] [-DeadlineDateTime <DateTime>] [-DisableWildcardHandling] [-EnableMomAlert <Boolean>] [-EnableSoftDeadline <Boolean>] [-FailParameterValue <Int32>] [-ForceWildcardHandling] [-OverrideServiceWindow <Boolean>] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-PostponeDateTime <DateTime>] [-PreDeploy <Boolean>] [-RaiseMomAlertsOnFailure <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-ReplaceToastNotificationWithDialog <Boolean>] [-RequireApproval <Boolean>] [-SendWakeUpPacket <Boolean>] [-SuccessParameterValue <Int32>] [-TimeBaseOn {LocalTime | Utc}] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationDeployment [-AllowRepairApp <Boolean>] -ApplicationName <String> [-AutoCloseExecutable <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-CreateAlertBaseOnPercentFailure <Boolean>] [-CreateAlertBaseOnPercentSuccess <Boolean>] [-DeadlineDateTime <DateTime>] [-DisableWildcardHandling] [-EnableMomAlert <Boolean>] [-EnableSoftDeadline <Boolean>] [-FailParameterValue <Int32>] [-ForceWildcardHandling] [-OverrideServiceWindow <Boolean>] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-PostponeDateTime <DateTime>] [-PreDeploy <Boolean>] [-RaiseMomAlertsOnFailure <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-ReplaceToastNotificationWithDialog <Boolean>] [-RequireApproval <Boolean>] [-SendWakeUpPacket <Boolean>] [-SuccessParameterValue <Int32>] [-TimeBaseOn {LocalTime | Utc}] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationDeployment [-AllowRepairApp <Boolean>] [-AutoCloseExecutable <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-CreateAlertBaseOnPercentFailure <Boolean>] [-CreateAlertBaseOnPercentSuccess <Boolean>] [-DeadlineDateTime <DateTime>] [-DisableWildcardHandling] [-EnableMomAlert <Boolean>] [-EnableSoftDeadline <Boolean>] [-FailParameterValue <Int32>] [-ForceWildcardHandling] -InputObject <IResultObject> [-OverrideServiceWindow <Boolean>] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-PostponeDateTime <DateTime>] [-PreDeploy <Boolean>] [-RaiseMomAlertsOnFailure <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-ReplaceToastNotificationWithDialog <Boolean>] [-RequireApproval <Boolean>] [-SendWakeUpPacket <Boolean>] [-SuccessParameterValue <Int32>] [-TimeBaseOn {LocalTime | Utc}] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
