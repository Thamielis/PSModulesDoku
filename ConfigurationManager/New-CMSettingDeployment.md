New-CMSettingDeployment
-----------------------




### Synopsis
Deploy a settings policy object to a collection.



---


### Description

Deploy a settings policy object to a collection. For example, deploy a BitLocker management policy or a Microsoft Defender Application Control policy. To create a custom schedule, use the New-CMSchedule (New-CMSchedule.md) cmdlet. To get a collection, use the [Get-CMCollection](Get-CMCollection.md)cmdlet.



---


### Related Links
* [Get-CMBlmSetting](Get-CMBlmSetting)



* [New-CMBlmSetting](New-CMBlmSetting)



* [Get-CMWdacSetting](Get-CMWdacSetting)



* [New-CMWdacSetting](New-CMWdacSetting)



* [Get-CMCollection](Get-CMCollection)



* [New-CMSchedule](New-CMSchedule)



* [Get-CMSettingDeployment](Get-CMSettingDeployment)



* [Remove-CMSettingDeployment](Remove-CMSettingDeployment)



* [Set-CMSettingDeployment](Set-CMSettingDeployment)





---


### Examples
#### Example 1: Deploy a BitLocker management object to all desktop and server clients
```PowerShell
$setting = Get-CMBlmSetting -Name "My BitLocker settings"

$collection = Get-CMCollection -Name "All Desktop and Server Clients"

New-CMSettingDeployment -CMSetting $setting -CollectionName $collection.Name
```

#### Example 2: Deploy a Windows Defender Application Control setting using a custom schedule
```PowerShell
$setting = Get-CMWdacSetting -Name "My App Control settings"

$collection = Get-CMCollection -Name "All Desktop and Server Clients"

$sched = New-CMSchedule -Start ((Get-Date).AddDays(-30)).ToString() -RecurCount 7 -RecurInterval Minutes

$dep = New-CMSettingDeployment -CMSetting $setting -Collection $collection -Schedule $sched
```



---


### Parameters
#### **CMSetting**

Specify a settings object to deploy.


* For BitLocker management, use the Get-CMBlmSetting (Get-CMBlmSetting.md) or [New-CMBlmSetting](New-CMBlmSetting.md)cmdlets. - For Microsoft Defender Application Control, use the Get-CMWdacSetting (Get-CMWdacSetting.md) or [New-CMWdacSetting](New-CMWdacSetting.md)cmdlets.






|Type          |Required|Position|PipelineInput |
|--------------|--------|--------|--------------|
|`[CMSettings]`|true    |1       |True (ByValue)|



#### **Collection**

Specify a collection object as the target for the deployment. To get a collection, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify the ID of the collection as the target for the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the name of the collection as the target for the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **OverrideServiceWindows**

When you add this parameter, the client can remediate the settings outside of a maintenance window.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Schedule**

Specify a schedule object to apply to the deployment. To create a custom schedule, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.SimplifiedSettings.CMSettings





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.Deployments.SettingsDeployment.SettingsDeployment






---


### Notes




---


### Syntax
```PowerShell
New-CMSettingDeployment [-CMSetting] <CMSettings> [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-OverrideServiceWindows] [-Schedule <IResultObject>] [<CommonParameters>]
```
