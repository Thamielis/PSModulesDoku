New-CMApplicationGroupDeployment
--------------------------------




### Synopsis
Create a deployment for an application group.



---


### Description

Create a deployment for an application group. An app group contains multiple applications, and users see the group in Software Center as a single entity. For more information, see Create application groups (/mem/configmgr/apps/deploy-use/create-app-groups).



Before you can deploy an app group, you need to create it. Then you can deploy it to a user or device collection as a single deployment.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplicationGroupDeployment](Get-CMApplicationGroupDeployment)



* [Remove-CMApplicationGroupDeployment](Remove-CMApplicationGroupDeployment)



* [Set-CMApplicationGroupDeployment](Set-CMApplicationGroupDeployment)



* [Get-CMApplicationGroup](Get-CMApplicationGroup)



* [Create application groups](Create application groups)





---


### Examples
#### Example 1
```PowerShell
$collection = Get-CMCollection -Name "co1"

$distributionPointName = "dp1.contoso.com"

New-CMApplicationGroupDeployment -Id 16777536 -Collection $collection -DistributionPointName $distributionPointName -DistributeContent
```



---


### Parameters
#### **AvailableDateTime**

Specify a DateTime object for when this deployment is available . To get this object, use the Get-Date (/powershell/module/microsoft.powershell.utility/get-date)built-in cmdlet.


Use DeadlineDateTime to specify the deployment assignment, or deadline .






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **Collection**

Specify a collection object as the target for this app group deployment. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify a collection ID as the target for this app group deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify a collection name as the target for this app group deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specify an optional comment for the app group deployment.






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

Specify whether this deployment is to install or uninstall the app group.



Valid Values:

* Install
* Uninstall






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[DeployActionType]`|false   |named   |False        |



#### **DeployPurpose**

Specify whether this deployment is available for users to install, or it's required to install at the deadline.



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



#### **DistributeCollectionName**

The site distributes content to the distribution point groups that are associated with this collection name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DistributeContent**

Add this parameter to distribute the app group content when you create this deployment. Clients can't install the applications until you distribute content to distribution points that the clients can access.






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



#### **EnableMomAlert**

Set this parameter to `$true` to enable System Center Operations Manager maintenance mode for this deployment.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateScomAlertOnFailure**

Set this parameter to `$true` to generate a System Center Operations Manager alert when the deployment fails.






|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |RaiseMomAlertsOnFailure|



#### **Id**

Specify the ID of the application group to deploy.






|Type     |Required|Position|PipelineInput|Aliases                              |
|---------|--------|--------|-------------|-------------------------------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID<br/>ApplicationGroupId|



#### **InputObject**

Specify an object for the app group. To get this object, use the Get-CMApplicationGroup (Get-CMApplicationGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |0       |True (ByValue)|ApplicationGroup|



#### **Name**

Specify a name for this app group deployment.






|Type      |Required|Position|PipelineInput|Aliases                                      |
|----------|--------|--------|-------------|---------------------------------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName<br/>ApplicationGroupName|



#### **OverrideServiceWindow**

Set this parameter to `$true` to install the app group outside a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PersistOnWriteFilterDevice**

Use this parameter to handle write filters for Windows Embedded devices. If you set it to `$true`, the device commits changes at the deadline or during a maintenance window. This action requires a restart. If you set it to `$false`, the device saves changes to the temporary overlay and commits them later.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RebootOutsideServiceWindow**

Set this parameter to `$true` to allow the device to restart outside a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SendWakeupPacket**

Indicates whether to send a wake-up packet to computers before the deployment begins. If this value is `$True`, Configuration Manager wakes a computer from sleep. If this value is `$False`, it doesn't wake computers from sleep. For computers to wake, first configure Wake On LAN.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **TimeBaseOn**

Specify which time zone to use:


* `LocalTime`: Use the local time of the device.


* `UTC`: Use Coordinated Universal Time (UTC).



Valid Values:

* LocalTime
* Utc






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[TimeType]`|false   |named   |False        |



#### **UseMeteredNetwork**

Indicates whether to allow clients on a metered internet connection to download content after the installation deadline, which might incur additional costs.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UserNotification**

Use this parameter to specify the user experience for this deployment:


* `DisplayAll`: Display in Software Center and show all notifications


* `DisplaySoftwareCenterOnly`: Display in Software Center, and only show notifications of computer restarts.


* `HideAll`: Hide in Software Center and all notifications



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
* IResultObject#SMS_ApplicationGroupAssignment






---


### Notes
This cmdlet returns the SMS_ApplicationGroupAssignment WMI class object.



---


### Syntax
```PowerShell
New-CMApplicationGroupDeployment [-Id] <Int32> [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployAction {Install | Uninstall}] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-EnableMomAlert <Boolean>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-OverrideServiceWindow <Boolean>] [-PersistOnWriteFilterDevice <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-SendWakeupPacket <Boolean>] [-TimeBaseOn {LocalTime | Utc}] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMApplicationGroupDeployment [-InputObject] <IResultObject> [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployAction {Install | Uninstall}] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-EnableMomAlert <Boolean>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-OverrideServiceWindow <Boolean>] [-PersistOnWriteFilterDevice <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-SendWakeupPacket <Boolean>] [-TimeBaseOn {LocalTime | Utc}] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMApplicationGroupDeployment [-Name] <String> [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DeployAction {Install | Uninstall}] [-DeployPurpose {Available | Required}] [-DisableWildcardHandling] [-DistributeCollectionName <String>] [-DistributeContent] [-DistributionPointGroupName <String>] [-DistributionPointName <String>] [-EnableMomAlert <Boolean>] [-ForceWildcardHandling] [-GenerateScomAlertOnFailure <Boolean>] [-OverrideServiceWindow <Boolean>] [-PersistOnWriteFilterDevice <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-SendWakeupPacket <Boolean>] [-TimeBaseOn {LocalTime | Utc}] [-UseMeteredNetwork <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
