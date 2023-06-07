Get-CMNotification
------------------




### Synopsis
{{ Fill in the Synopsis }}



---


### Description

{{ Fill in the Description }}



---


### Examples
#### Example 1
```PowerShell
PS C:\> {{ Add example code here }}
```
{{ Add example description here }}


---


### Parameters
#### **DisableWildcardHandling**

{{ Fill DisableWildcardHandling Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

{{ Fill ForceWildcardHandling Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

{{ Fill Id Description }}






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |TaskId<br/>Task_Id|



#### **Name**

{{ Fill Name Description }}






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|false   |named   |False        |TaskName<br/>Task_Name|



#### **Type**

{{ Fill Type Description }}



Valid Values:

* SiteVersionOutOfSupport
* ConsoleVersionMismatch
* SiteReadonly
* SiteVersionToBeExpired
* EvalVersionExpired
* EvalVersionApproachExpiration
* UpdatePackageAvailable
* SiteBusy
* CloudConnectorMissing
* PushNotificationsStayInformed
* PushNotificationsPlanForChange
* PushNotificationsFixIssue
* OfficeAdrObsoleteChannelName
* AzureTenantCertApproachExpiration
* AzureTenantCertExpired
* ManagementInsightsWin10OutOfSupport
* ManagementInsightsWin7OutOfSupport
* ConsoleCustomExtensionsFound
* CloudConnectivityBroken
* AzureTenantCertCloseToExpiration
* ManagementInsightsGeneric
* CloudAttachOnboard






|Type                  |Required|Position|PipelineInput|Aliases|
|----------------------|--------|--------|-------------|-------|
|`[NotificationType[]]`|true    |named   |False        |Types  |





---


### Inputs
None





---


### Outputs
* ConnectionManagerNotificationTaskBase


* ConnectionManagerNotificationTaskBase[]






---


### Notes




---


### Syntax
```PowerShell
Get-CMNotification [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMNotification [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
```PowerShell
Get-CMNotification [-DisableWildcardHandling] [-ForceWildcardHandling] -Type {SiteVersionOutOfSupport | ConsoleVersionMismatch | SiteReadonly | SiteVersionToBeExpired | EvalVersionExpired | EvalVersionApproachExpiration | UpdatePackageAvailable | SiteBusy | CloudConnectorMissing | PushNotificationsStayInformed | PushNotificationsPlanForChange | PushNotificationsFixIssue | OfficeAdrObsoleteChannelName | AzureTenantCertApproachExpiration | AzureTenantCertExpired | ManagementInsightsWin10OutOfSupport | ManagementInsightsWin7OutOfSupport | ConsoleCustomExtensionsFound | CloudConnectivityBroken | AzureTenantCertCloseToExpiration | ManagementInsightsGeneric | CloudAttachOnboard} [<CommonParameters>]
```
