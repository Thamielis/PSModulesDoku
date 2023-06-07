Set-CMApplicationGroupDeployment
--------------------------------




### Synopsis
Configure the deployment of an application group.



---


### Description

Configure the deployment of an application group. An app group contains multiple applications, and users see the group in Software Center as a single entity. For more information, see Create application groups (/mem/configmgr/apps/deploy-use/create-app-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplicationGroupDeployment](Get-CMApplicationGroupDeployment)



* [New-CMApplicationGroupDeployment](New-CMApplicationGroupDeployment)



* [Remove-CMApplicationGroupDeployment](Remove-CMApplicationGroupDeployment)



* [Get-CMApplicationGroup](Get-CMApplicationGroup)



* [Create application groups](Create application groups)





---


### Examples
#### Example 1
```PowerShell
$collection = Get-CMCollection -Name "co1"

Set-CMApplicationGroupDeployment -ApplicationGroupName "appGroupTest" -Collection $collection -Comment "modify comment"
```



---


### Parameters
#### **ApplicationGroudId**

Specify the ID of the app group to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ApplicationGroupName**

Specify the name of the app group to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an object for the app group. To get this object, use the Get-CMApplicationGroup (Get-CMApplicationGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                                                              |
|-----------------|--------|--------|--------------|---------------------------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ApplicationGroup<br/>DeploymentSummary<br/>ApplicationGroupAssignment|



#### **OverrideServiceWindow**

Set this parameter to `$true` to install the app group outside a maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PersistOnWriteFilterDevice**

Use this parameter to handle write filters for Windows Embedded devices. If you set it to `$true`, the device commits changes at the deadline or during a maintenance window. This action requires a restart. If you set it to `$false`, the device saves changes to the temporary overlay and commits them later.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RaiseMomAlertsOnFailure**

Set this parameter to `$true` to generate a System Center Operations Manager alert when the deployment fails.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RebootOutsideServiceWindow**

Set this parameter to `$true` to allow the device to restart outside a maintenance window.






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


* IResultObject#SMS_DeploymentSummary






---


### Notes
This cmdlet returns the SMS_ApplicationGroupAssignment WMI class object.



---


### Syntax
```PowerShell
Set-CMApplicationGroupDeployment -ApplicationGroudId <String> [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DisableWildcardHandling] [-EnableMomAlert <Boolean>] [-ForceWildcardHandling] [-OverrideServiceWindow <Boolean>] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-RaiseMomAlertsOnFailure <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-TimeBaseOn {LocalTime | Utc}] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationGroupDeployment -ApplicationGroupName <String> [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DisableWildcardHandling] [-EnableMomAlert <Boolean>] [-ForceWildcardHandling] [-OverrideServiceWindow <Boolean>] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-RaiseMomAlertsOnFailure <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-TimeBaseOn {LocalTime | Utc}] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMApplicationGroupDeployment [-AvailableDateTime <DateTime>] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Comment <String>] [-DeadlineDateTime <DateTime>] [-DisableWildcardHandling] [-EnableMomAlert <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-OverrideServiceWindow <Boolean>] [-PassThru] [-PersistOnWriteFilterDevice <Boolean>] [-RaiseMomAlertsOnFailure <Boolean>] [-RebootOutsideServiceWindow <Boolean>] [-TimeBaseOn {LocalTime | Utc}] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
