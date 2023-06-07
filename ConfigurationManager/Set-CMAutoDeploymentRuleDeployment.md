Set-CMAutoDeploymentRuleDeployment
----------------------------------




### Synopsis
Sets a deployment for an automatic deployment rule.



---


### Description

The Set-CMAutoDeploymentRuleDeployment cmdlet updates a deployment for an automatic deployment rule.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCollection](Get-CMCollection)



* [Get-CMAutoDeploymentRuleDeployment](Get-CMAutoDeploymentRuleDeployment)



* [Get-CMSoftwareUpdateAutoDeploymentRule](Get-CMSoftwareUpdateAutoDeploymentRule)



* [New-CMAutoDeploymentRuleDeployment](New-CMAutoDeploymentRuleDeployment)



* [Remove-CMAutoDeploymentRuleDeployment](Remove-CMAutoDeploymentRuleDeployment)





---


### Examples
#### Example 1: Set a deployment by ID
```PowerShell
PS XYZ:\> Set-CMAutoDeploymentRuleDeployment -ID 348 -CollectionName "All Systems" -EnableDeployment $True -SendWakeupPacket $False -VerboseLevel OnlySuccessAndErrorMessages -UseUtc $False  -AvailableTime 7 -AvailableTimeUnit Days -DeadlineTime 7 -DeadlineTimeUnit Days -UserNotification DisplaySoftwareCenterOnly -AllowSoftwareInstallationOutsideMaintenanceWindow $False -AllowRestart $False -SuppressRestartServer  $False -SuppressRestartWorkstation $False -WriteFilterHandling $False -GenerateSuccessAlert $True -SuccessPercentage 10 -AlertTime 7 -AlertTimeUnit Days -DisableOperationsManager $False -GenerateOperationsManagerAlert $False -NoInstallOnRemote $False -NoInstallOnUnprotected $False -UseBranchCache $False
```
This command updates the settings for the deployment rule deployment with the action ID of 348 and the collection named All Systems.
#### Example 2: Set a deployment using a variable
```PowerShell
PS XYZ:\> $ReferenceADR = Get-CMAutoDeploymentRule -Name "TestADR01"
PS XYZ:\> $Deployment = $ReferenceADR | Get-CMAutoDeploymentRuleDeployment
PS XYZ:\> Set-CMAutoDeploymentRuleDeployment -InputObject $Deployment[0] -CollectionName "All Systems" -EnableDeployment $True -SendWakeupPacket $False -VerboseLevel OnlySuccessAndErrorMessages -UseUtc $False -AvailableTime 7 -AvailableTimeUnit Days -DeadlineTime 7 -DeadlineTimeUnit Days -UserNotification DisplaySoftwareCenterOnly -AllowSoftwareInstallationOutsideMaintenanceWindow $False -AllowRestart $False -SuppressRestartServer $False -SuppressRestartWorkstation $False -WriteFilterHandling $False -GenerateSuccessAlert $True -SuccessPercentage 10 -AlertTime 7 -AlertTimeUnit Days -DisableOperationsManager $False -GenerateOperationsManagerAlert $False -NoInstallOnRemote $False -NoInstallOnUnprotected $False -UseBranchCache $False
```
The first command gets the automatic deployment rule object named TestADR01 and stores the object in the $ReferenceADR variable.


The second command gets the deployments associated with the automatic deployment rule object stored in $ReferenceADR and stores the deployments in the $Deployment variable.


The last command updates the settings for the first deployment stored in $Deployment.


---


### Parameters
#### **AlertTime**

Specifies the number of time units for the offset from the deadline.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **AlertTimeUnit**

Specifies the time unit type for the offset from the deadline. Valid values are:


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



#### **AllowDownloadFromMicrosoftUpdate**

Use this parameter to set the following option on the Download Settings page of the ADR deployment settings: If software updates are not available on distribution point in current, neighbor or site boundary groups, download content from Microsoft Updates .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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

Use this parameter to set the following option on the Download Settings page of the ADR deployment settings: Allow clients on a metered Internet connection to download content after the installation deadline, which might incur additionl costs






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AvailableImmediately**

Indicates whether software updates are available to install as soon as possible after the rule is run.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AvailableTime**

Specifies the number of time units for the software available time.






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

Specifies a target collection object for the software update deployment. To obtain a collection object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specifies the ID of the target collection for the software update deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specifies the name of the target collection for the software update deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **DisableOperationsManager**

Indicates whether Operations Manager alerts are disabled while software updates run.






|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |DisableOperationManager|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableDeployment**

Indicates whether to enable the deployment after this rule runs for the associated software group. If set to $False, you must manually deploy the software update group.






|Type       |Required|Position|PipelineInput|Aliases                                            |
|-----------|--------|--------|-------------|---------------------------------------------------|
|`[Boolean]`|false   |named   |False        |Enable<br/>EnabledAfterCreate<br/>EnableAfterCreate|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateOperationsManagerAlert**

Indicates whether Operations Manager alerts are generated when a software update installation fails.






|Type       |Required|Position|PipelineInput|Aliases                      |
|-----------|--------|--------|-------------|-----------------------------|
|`[Boolean]`|false   |named   |False        |GenerateOperationManagerAlert|



#### **GenerateSuccessAlert**

Indicates whether an alert is generated when this rule runs successfully.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Id**

Specifies the action ID of the automatic deployment rule deployment.






|Type     |Required|Position|PipelineInput|Aliases |
|---------|--------|--------|-------------|--------|
|`[Int32]`|true    |0       |False        |ActionID|



#### **InputObject**

Specifies an automatic deployment rule object. To obtain an automatic deployment rule object, use the Get-CMSoftwareUpdateAutoDeploymentRule (Get-CMSoftwareUpdateAutoDeploymentRule.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                     |
|-----------------|--------|--------|--------------|----------------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|AutoDeploymentRuleDeployment|



#### **NoInstallOnRemote**

Indicates whether to install software updates when the updates are not available on any remote distribution points.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **NoInstallOnUnprotected**

Indicates whether to install software updates when the updates are not available on any unprotected distribution points.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RequirePostRebootFullScan**

Use this parameter to set the following option on the User Experience page of the ADR deployment settings: If any update in this deployment requires a system restart, run updates deployment evaluation cycle after restart .






|Type       |Required|Position|PipelineInput|Aliases                  |
|-----------|--------|--------|-------------|-------------------------|
|`[Boolean]`|false   |named   |False        |RunEvaluationAfterRestart|



#### **SendWakeupPacket**

Indicates whether to use Wake-on-LAN to wake up clients for required deployments.






|Type       |Required|Position|PipelineInput|Aliases        |
|-----------|--------|--------|-------------|---------------|
|`[Boolean]`|false   |named   |False        |EnableWakeOnLan|



#### **SoftDeadlineEnabled**

Use this parameter to set the following option on the Deployment Schedule page of the ADR deployment settings: Delay enforcement of this deployment according to user preferences, up to the grace period defined in client settings .






|Type       |Required|Position|PipelineInput|Aliases                           |
|-----------|--------|--------|-------------|----------------------------------|
|`[Boolean]`|false   |named   |False        |DelayEnforcementAndUpToGracePeriod|



#### **SuccessPercentage**

Specifies the percent, as an integer, of client compliance. When client compliance falls below this percentage, an alert is generated.






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



#### **UseBranchCache**

Indicates whether clients are allowed to share content with other clients on the same subnet.






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






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[UserNotificationOption]`|false   |named   |False        |



#### **UseUtc**

Indicates whether the schedule for this deployment is evaluated based upon Universal Coordinated Time (UTC).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **VerboseLevel**

Specifies how much state detail the clients report back for deployments created by this rule. Valid values are:


* OnlyErrorMessages


* OnlySuccessAndErrorMessages


* AllMessages



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_AdrDeploymentSettings






---


### Notes




---


### Syntax
```PowerShell
Set-CMAutoDeploymentRuleDeployment [-Id] <Int32> [-AlertTime <Int32>] [-AlertTimeUnit {Hours | Days | Weeks | Months}] [-AllowDownloadFromMicrosoftUpdate <Boolean>] [-AllowRestart <Boolean>] [-AllowSoftwareInstallationOutsideMaintenanceWindow <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-AvailableImmediately <Boolean>] [-AvailableTime <Int32>] [-AvailableTimeUnit {Hours | Days | Weeks | Months}] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeadlineImmediately <Boolean>] [-DeadlineTime <Int32>] [-DeadlineTimeUnit {Hours | Days | Weeks | Months}] [-DisableOperationsManager <Boolean>] [-DisableWildcardHandling] [-EnableDeployment <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-NoInstallOnRemote <Boolean>] [-NoInstallOnUnprotected <Boolean>] [-PassThru] [-RequirePostRebootFullScan <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SuccessPercentage <Int32>] [-SuppressRestartServer <Boolean>] [-SuppressRestartWorkstation <Boolean>] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseUtc <Boolean>] [-VerboseLevel {OnlyErrorMessages | OnlySuccessAndErrorMessages | AllMessages}] [-WriteFilterHandling <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAutoDeploymentRuleDeployment [-InputObject] <IResultObject> [-AlertTime <Int32>] [-AlertTimeUnit {Hours | Days | Weeks | Months}] [-AllowDownloadFromMicrosoftUpdate <Boolean>] [-AllowRestart <Boolean>] [-AllowSoftwareInstallationOutsideMaintenanceWindow <Boolean>] [-AllowUseMeteredNetwork <Boolean>] [-AvailableImmediately <Boolean>] [-AvailableTime <Int32>] [-AvailableTimeUnit {Hours | Days | Weeks | Months}] [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeadlineImmediately <Boolean>] [-DeadlineTime <Int32>] [-DeadlineTimeUnit {Hours | Days | Weeks | Months}] [-DisableOperationsManager <Boolean>] [-DisableWildcardHandling] [-EnableDeployment <Boolean>] [-ForceWildcardHandling] [-GenerateOperationsManagerAlert <Boolean>] [-GenerateSuccessAlert <Boolean>] [-NoInstallOnRemote <Boolean>] [-NoInstallOnUnprotected <Boolean>] [-PassThru] [-RequirePostRebootFullScan <Boolean>] [-SendWakeupPacket <Boolean>] [-SoftDeadlineEnabled <Boolean>] [-SuccessPercentage <Int32>] [-SuppressRestartServer <Boolean>] [-SuppressRestartWorkstation <Boolean>] [-UseBranchCache <Boolean>] [-UserNotification {DisplayAll | DisplaySoftwareCenterOnly | HideAll}] [-UseUtc <Boolean>] [-VerboseLevel {OnlyErrorMessages | OnlySuccessAndErrorMessages | AllMessages}] [-WriteFilterHandling <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
