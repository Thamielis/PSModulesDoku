Invoke-CMClientAction
---------------------




### Synopsis
Sends a notification to client computers to trigger an immediate client action.



---


### Description

The Invoke-CMClientAction cmdlet sends a notification to client computers to trigger an immediate client action. You can specify one or more client computers, or send a notification to all the computers in a specified device collection.



For more information about these actions, see Client notification (/mem/configmgr/core/clients/manage/client-notification).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDevice](Get-CMDevice)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Client notifications](Client notifications)





---


### Examples
#### Example 1: Wake up a device
```PowerShell
Invoke-CMClientAction -DeviceName "SleepDevice01" -ActionType ClientNotificationWakeUpClientNow -ParentCollectionId $col.CollectionID
```

#### Example 2: Request machine policy from a device
```PowerShell
Invoke-CMClientAction -DeviceName "Computer073" -NotificationType RequestMachinePolicyNow
```



---


### Parameters
#### **ActionType**

Specify an action keyword to send to the client. To request machine or user policy, use the -NotificationType parameter.



Valid Values:

* None
* EndpointProtectionFullScan
* EndpointProtectionQuickScan
* EndpointProtectionDownloadDefinition
* EndpointProtectionEvaluateSoftwareUpdate
* EndpointProtectionExcludeScanPaths
* EndpointProtectionAllowThreat
* EndpointProtectionRestoreQuarantinedItems
* ClientNotificationRequestMachinePolicyNow
* ClientNotificationRequestUsersPolicyNow
* ClientNotificationRequestDDRNow
* ClientNotificationRequestSWInvNow
* ClientNotificationRequestHWInvNow
* ClientNotificationAppDeplEvalNow
* ClientNotificationSUMDeplEvalNow
* ClientRequestSUPChangeNow
* ClientRequestDHAChangeNow
* ClientNotificationRebootMachine
* DiagnosticsEnableVerboseLogging
* DiagnosticsDisableVerboseLogging
* DiagnosticsCollectFiles
* EndpointProtectionRestoreWithDeps
* ClientNotificationCheckComplianceNow
* RequestScriptExecution
* RequestCMPivotExecution
* ClientNotificationWakeUpClientNow






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[ClientActionType]`|false   |named   |False        |



#### **Collection**

Specify a collection object to target.






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeviceCollection|



#### **CollectionId**

Specify a collection by ID to target.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |DeviceCollectionId|



#### **CollectionName**

Specify a collection by name to target.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |DeviceCollectionName|



#### **Device**

Specify a device object to target.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DeviceId**

Specify a device by ID to target.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |ResourceId|



#### **DeviceName**

Specify a device by name to target.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NotificationType**

Request machine or user policy from a client. To trigger all other actions, use the -ActionType parameter.



Valid Values:

* RequestMachinePolicyNow
* RequestUsersPolicyNow






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[ClientNotificationType]`|false   |named   |False        |



#### **ParentCollection**

Use this parameter to support waking up a machine.






|Type             |Required|Position|PipelineInput|Aliases               |
|-----------------|--------|--------|-------------|----------------------|
|`[IResultObject]`|false   |named   |False        |ParentDeviceCollection|



#### **ParentCollectionId**

Use this parameter to support waking up a machine.






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|false   |named   |False        |ParentDeviceCollectionId|



#### **ParentCollectionName**

Use this parameter to support waking up a machine.






|Type      |Required|Position|PipelineInput|Aliases                   |
|----------|--------|--------|-------------|--------------------------|
|`[String]`|false   |named   |False        |ParentDeviceCollectionName|



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
Cmdlet aliases: Invoke-CMClientNotification



---


### Syntax
```PowerShell
Invoke-CMClientAction [-ActionType {None | EndpointProtectionFullScan | EndpointProtectionQuickScan | EndpointProtectionDownloadDefinition | EndpointProtectionEvaluateSoftwareUpdate | EndpointProtectionExcludeScanPaths | EndpointProtectionAllowThreat | EndpointProtectionRestoreQuarantinedItems | ClientNotificationRequestMachinePolicyNow | ClientNotificationRequestUsersPolicyNow | ClientNotificationRequestDDRNow | ClientNotificationRequestSWInvNow | ClientNotificationRequestHWInvNow | ClientNotificationAppDeplEvalNow | ClientNotificationSUMDeplEvalNow | ClientRequestSUPChangeNow | ClientRequestDHAChangeNow | ClientNotificationRebootMachine | DiagnosticsEnableVerboseLogging | DiagnosticsDisableVerboseLogging | DiagnosticsCollectFiles | EndpointProtectionRestoreWithDeps | ClientNotificationCheckComplianceNow | RequestScriptExecution | RequestCMPivotExecution | ClientNotificationWakeUpClientNow}] -Collection <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-NotificationType {RequestMachinePolicyNow | RequestUsersPolicyNow}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMClientAction [-ActionType {None | EndpointProtectionFullScan | EndpointProtectionQuickScan | EndpointProtectionDownloadDefinition | EndpointProtectionEvaluateSoftwareUpdate | EndpointProtectionExcludeScanPaths | EndpointProtectionAllowThreat | EndpointProtectionRestoreQuarantinedItems | ClientNotificationRequestMachinePolicyNow | ClientNotificationRequestUsersPolicyNow | ClientNotificationRequestDDRNow | ClientNotificationRequestSWInvNow | ClientNotificationRequestHWInvNow | ClientNotificationAppDeplEvalNow | ClientNotificationSUMDeplEvalNow | ClientRequestSUPChangeNow | ClientRequestDHAChangeNow | ClientNotificationRebootMachine | DiagnosticsEnableVerboseLogging | DiagnosticsDisableVerboseLogging | DiagnosticsCollectFiles | EndpointProtectionRestoreWithDeps | ClientNotificationCheckComplianceNow | RequestScriptExecution | RequestCMPivotExecution | ClientNotificationWakeUpClientNow}] -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-NotificationType {RequestMachinePolicyNow | RequestUsersPolicyNow}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMClientAction [-ActionType {None | EndpointProtectionFullScan | EndpointProtectionQuickScan | EndpointProtectionDownloadDefinition | EndpointProtectionEvaluateSoftwareUpdate | EndpointProtectionExcludeScanPaths | EndpointProtectionAllowThreat | EndpointProtectionRestoreQuarantinedItems | ClientNotificationRequestMachinePolicyNow | ClientNotificationRequestUsersPolicyNow | ClientNotificationRequestDDRNow | ClientNotificationRequestSWInvNow | ClientNotificationRequestHWInvNow | ClientNotificationAppDeplEvalNow | ClientNotificationSUMDeplEvalNow | ClientRequestSUPChangeNow | ClientRequestDHAChangeNow | ClientNotificationRebootMachine | DiagnosticsEnableVerboseLogging | DiagnosticsDisableVerboseLogging | DiagnosticsCollectFiles | EndpointProtectionRestoreWithDeps | ClientNotificationCheckComplianceNow | RequestScriptExecution | RequestCMPivotExecution | ClientNotificationWakeUpClientNow}] -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-NotificationType {RequestMachinePolicyNow | RequestUsersPolicyNow}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMClientAction [-ActionType {None | EndpointProtectionFullScan | EndpointProtectionQuickScan | EndpointProtectionDownloadDefinition | EndpointProtectionEvaluateSoftwareUpdate | EndpointProtectionExcludeScanPaths | EndpointProtectionAllowThreat | EndpointProtectionRestoreQuarantinedItems | ClientNotificationRequestMachinePolicyNow | ClientNotificationRequestUsersPolicyNow | ClientNotificationRequestDDRNow | ClientNotificationRequestSWInvNow | ClientNotificationRequestHWInvNow | ClientNotificationAppDeplEvalNow | ClientNotificationSUMDeplEvalNow | ClientRequestSUPChangeNow | ClientRequestDHAChangeNow | ClientNotificationRebootMachine | DiagnosticsEnableVerboseLogging | DiagnosticsDisableVerboseLogging | DiagnosticsCollectFiles | EndpointProtectionRestoreWithDeps | ClientNotificationCheckComplianceNow | RequestScriptExecution | RequestCMPivotExecution | ClientNotificationWakeUpClientNow}] -Device <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-NotificationType {RequestMachinePolicyNow | RequestUsersPolicyNow}] [-ParentCollection <IResultObject>] [-ParentCollectionId <String>] [-ParentCollectionName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMClientAction [-ActionType {None | EndpointProtectionFullScan | EndpointProtectionQuickScan | EndpointProtectionDownloadDefinition | EndpointProtectionEvaluateSoftwareUpdate | EndpointProtectionExcludeScanPaths | EndpointProtectionAllowThreat | EndpointProtectionRestoreQuarantinedItems | ClientNotificationRequestMachinePolicyNow | ClientNotificationRequestUsersPolicyNow | ClientNotificationRequestDDRNow | ClientNotificationRequestSWInvNow | ClientNotificationRequestHWInvNow | ClientNotificationAppDeplEvalNow | ClientNotificationSUMDeplEvalNow | ClientRequestSUPChangeNow | ClientRequestDHAChangeNow | ClientNotificationRebootMachine | DiagnosticsEnableVerboseLogging | DiagnosticsDisableVerboseLogging | DiagnosticsCollectFiles | EndpointProtectionRestoreWithDeps | ClientNotificationCheckComplianceNow | RequestScriptExecution | RequestCMPivotExecution | ClientNotificationWakeUpClientNow}] -DeviceId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-NotificationType {RequestMachinePolicyNow | RequestUsersPolicyNow}] [-ParentCollection <IResultObject>] [-ParentCollectionId <String>] [-ParentCollectionName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMClientAction [-ActionType {None | EndpointProtectionFullScan | EndpointProtectionQuickScan | EndpointProtectionDownloadDefinition | EndpointProtectionEvaluateSoftwareUpdate | EndpointProtectionExcludeScanPaths | EndpointProtectionAllowThreat | EndpointProtectionRestoreQuarantinedItems | ClientNotificationRequestMachinePolicyNow | ClientNotificationRequestUsersPolicyNow | ClientNotificationRequestDDRNow | ClientNotificationRequestSWInvNow | ClientNotificationRequestHWInvNow | ClientNotificationAppDeplEvalNow | ClientNotificationSUMDeplEvalNow | ClientRequestSUPChangeNow | ClientRequestDHAChangeNow | ClientNotificationRebootMachine | DiagnosticsEnableVerboseLogging | DiagnosticsDisableVerboseLogging | DiagnosticsCollectFiles | EndpointProtectionRestoreWithDeps | ClientNotificationCheckComplianceNow | RequestScriptExecution | RequestCMPivotExecution | ClientNotificationWakeUpClientNow}] -DeviceName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-NotificationType {RequestMachinePolicyNow | RequestUsersPolicyNow}] [-ParentCollection <IResultObject>] [-ParentCollectionId <String>] [-ParentCollectionName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
