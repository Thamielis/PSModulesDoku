New-CMApplicationDeployment
---------------------------




### Synopsis
Create an application deployment.



---


### Description

The New-CMApplicationDeployment cmdlet creates an application deployment. For more information, see Deploy applications with Configuration Manager (/mem/configmgr/apps/deploy-use/deploy-applications).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplication](Get-CMApplication)



* [Get-CMApplicationDeployment](Get-CMApplicationDeployment)



* [Remove-CMApplicationDeployment](Remove-CMApplicationDeployment)



* [Set-CMApplicationDeployment](Set-CMApplicationDeployment)



* [Deploy applications with Configuration Manager](Deploy applications with Configuration Manager)





---


### Examples
#### Example 1: Install an application
```PowerShell
New-CMApplicationDeployment -Name "Visual Studio 2019" -AvailableDateTime '01/01/2020 00:00:00' -CollectionName 'Developers Workstation' -DeadlineDateTime '01/01/2020 00:00:00' -DeployAction Install -DeployPurpose Required
```



---


### Parameters
#### **AllowRepairApp**

Use this parameter to configure the repair application option when creating a deployment for an application.






|Type       |Required|Position|PipelineInput|Aliases                   |
|-----------|--------|--------|-------------|--------------------------|
|`[Boolean]`|false   |named   |False        |AllowUserRepairApplication|



#### **ApprovalRequired**

If you set this parameter to `$true`, an administrator must approve a request for this application on the device.






|Type       |Required|Position|PipelineInput|Aliases            |
|-----------|--------|--------|-------------|-------------------|
|`[Boolean]`|false   |named   |False        |AppRequiresApproval|



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

Specify the ID of the collection to which this application is deployed. For example, `"SMS00004"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the name of the collection to which this application is deployed.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specify an optional comment for this deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeadlineDateTime**

Specify a DateTime object for when this deployment is assigned, also known as the deadline . To get this object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)built-in cmdlet.


Use -AvailableDateTime to specify when the deployment is available .






|Type        |Required|Position|PipelineInput|Aliases                     |
|------------|--------|--------|-------------|----------------------------|
|`[DateTime]`|false   |named   |False        |SupersedenceDeadlineDateTime|



#### **DeployAction**

Specify the deployment action, either to install or uninstall the application. If competing deployments target the same device, the Install action takes priority.



Valid Values:

* Install
* Uninstall






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[DeployActionType]`|false   |named   |False        |



#### **DeployPurpose**

Specify the deployment purpose:


* `Available`: The user sees the application in Software Center. They can install it on demand.


* `Required`: The client automatically installs the app according to the schedule that you set. If the application isn't hidden, a user can track its deployment status. They can also use Software Center to install the application before the deadline.



Valid Values:

* Available
* Required






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[DeployPurposeType]`|false   |named   |False        |



#### **DisableContentDependencyDetection**

Add this parameter to not automatically distribute content for dependent apps.






|Type      |Required|Position|PipelineInput|Aliases                                   |
|----------|--------|--------|-------------|------------------------------------------|
|`[Switch]`|false   |named   |False        |DisableDetectAssociatedContentDependencies|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributeCollectionName**

The site distributes content to the distribution points that are associated with this collection name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DistributeContent**

Add this parameter if you need to distribute the app content first.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPointGroupName**

To distribute the application content, specify the name of a distribution point group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DistributionPointName**

To distribute the application content, specify the name of a distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **GenerateScomAlertOnFailure**

Indicates whether to create an Operations Manager alert if a client fails to install the application.






|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |RaiseMomAlertsOnFailure|



#### **Id**

Specify the ID of the application to deploy.






|Type     |Required|Position|PipelineInput|Aliases                         |
|---------|--------|--------|-------------|--------------------------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID<br/>ApplicationId|



#### **InputObject**

Specify an application object to deploy. To get this object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |0       |True (ByValue)|Application|



#### **Name**

Specify the name of the application to deploy.






|Type      |Required|Position|PipelineInput|Aliases                                 |
|----------|--------|--------|-------------|----------------------------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName<br/>ApplicationName|



#### **OverrideServiceWindow**

Indicates whether the deployment takes place even if scheduled outside of a maintenance window. A maintenance window is a specified period of time used for computer maintenance and updates. If this value is `$True`, Configuration Manager deploys the application even if the scheduled time falls outside the maintenance window. If this value is `$False`, Configuration Manager doesn't deploy the application outside the window. It waits until it can deploy in an available window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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



#### **SendWakeupPacket**

Indicates whether to send a wake-up packet to computers before the deployment begins. If this value is `$True`, Configuration Manager attempts to wake a computer from sleep. If this value is `$False`, it doesn't wake computers from sleep. For computers to wake, you must first configure Wake On LAN.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Simulation**

Add this parameter to create a deployment simulation. For more information, see Simulate application deployments with Configuration Manager (/mem/configmgr/apps/deploy-use/simulate-application-deployments).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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



#### **UpdateSupersedence**

For an available deployment, use this parameter to specify the installation deadline to upgrade users or devices that have the superseded application installed. Use DeadlineDateTime to specify a specific time, otherwise it's as soon as possible after the AvailableDateTime .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMApplicationDeployment [-Id] <Int32> [-AllowRepairApp <Boolean>] [-ApprovalRequired <Boolean>] [-AutoCloseExecutable <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployAction {Install | Uninstall}] [-DeployPurpose {Available | Required}] [-DisableContentDependencyDetection] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-EnableMomAlert <Boolean>] [-EnableSoftDeadline <Boolean>] [-FailParameterValue <Int32>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-OverrideServiceWindow <Boolean>] [-PersistOnWriteFilterDevice <Boolean>] [-PostponeDateTime <DateTime>] [-PreDeploy <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-ReplaceToastNotificationWithDialog <Boolean>] [-SendWakeupPacket <Boolean>] [-Simulation] [-SuccessParameterValue <Int32>] [-TimeBaseOn {LocalTime | Utc}] [-UpdateSupersedence <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMApplicationDeployment [-InputObject] <IResultObject> [-AllowRepairApp <Boolean>] [-ApprovalRequired <Boolean>] [-AutoCloseExecutable <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployAction {Install | Uninstall}] [-DeployPurpose {Available | Required}] [-DisableContentDependencyDetection] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-EnableMomAlert <Boolean>] [-EnableSoftDeadline <Boolean>] [-FailParameterValue <Int32>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-OverrideServiceWindow <Boolean>] [-PersistOnWriteFilterDevice <Boolean>] [-PostponeDateTime <DateTime>] [-PreDeploy <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-ReplaceToastNotificationWithDialog <Boolean>] [-SendWakeupPacket <Boolean>] [-Simulation] [-SuccessParameterValue <Int32>] [-TimeBaseOn {LocalTime | Utc}] [-UpdateSupersedence <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMApplicationDeployment [-Name] <String> [-AllowRepairApp <Boolean>] [-ApprovalRequired <Boolean>] [-AutoCloseExecutable <Boolean>] [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployAction {Install | Uninstall}] [-DeployPurpose {Available | Required}] [-DisableContentDependencyDetection] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-EnableMomAlert <Boolean>] [-EnableSoftDeadline <Boolean>] [-FailParameterValue <Int32>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-OverrideServiceWindow <Boolean>] [-PersistOnWriteFilterDevice <Boolean>] [-PostponeDateTime <DateTime>] [-PreDeploy <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-ReplaceToastNotificationWithDialog <Boolean>] [-SendWakeupPacket <Boolean>] [-Simulation] [-SuccessParameterValue <Int32>] [-TimeBaseOn {LocalTime | Utc}] [-UpdateSupersedence <Boolean>] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
