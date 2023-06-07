Set-CMSettingDeployment
-----------------------




### Synopsis
Configure an existing settings policy deployment.



---


### Description

Configure an existing settings policy deployment. For example, configure the deployment of a BitLocker management policy or a Microsoft Defender Application Control policy.



---


### Related Links
* [Get-CMSettingDeployment](Get-CMSettingDeployment)



* [New-CMSettingDeployment](New-CMSettingDeployment)



* [Remove-CMSettingDeployment](Remove-CMSettingDeployment)





---


### Examples
#### Example 1: Modify the schedule for the deployment of a BitLocker management policy
```PowerShell
Get-CMBlmSetting -Name "My BitLocker setting" | Get-CMSettingDeployment | Set-CMSettingDeployment -Schedule (New-CMSchedule -Start ((Get-Date).AddDays(-30)).ToString() -RecurCount 7 -RecurInterval Minutes)
```

#### Example 2: Configure the deployment of a Microsoft Defender Application Control policy
```PowerShell
Get-CMWdacSetting -Name "My App Control setting"  | Get-CMSettingDeployment | Set-CMSettingDeployment -OverrideServiceWindows
```



---


### Parameters
#### **CMSettingsDeployment**

Specify the settings deployment object to configure. To get the deployment object, use the Get-CMSettingDeployment (Get-CMSettingDeployment.md)cmdlet.






|Type                  |Required|Position|PipelineInput |
|----------------------|--------|--------|--------------|
|`[SettingsDeployment]`|true    |1       |True (ByValue)|



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






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






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
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.Deployments.SettingsDeployment.SettingsDeployment





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.Deployments.SettingsDeployment.SettingsDeployment






---


### Notes




---


### Syntax
```PowerShell
Set-CMSettingDeployment [-CMSettingsDeployment] <SettingsDeployment> [-DisableWildcardHandling] [-ForceWildcardHandling] [-OverrideServiceWindows <Boolean>] [-PassThru] [-Schedule <IResultObject>] [<CommonParameters>]
```
