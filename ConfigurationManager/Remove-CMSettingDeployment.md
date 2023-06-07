Remove-CMSettingDeployment
--------------------------




### Synopsis
Remove a deployment for a settings policy object.



---


### Description

Delete a deployment for a settings policy object. For example, remove the deployment of a BitLocker management policy or a Microsoft Defender Application Control policy.



---


### Related Links
* [Get-CMSettingDeployment](Get-CMSettingDeployment)



* [New-CMSettingDeployment](New-CMSettingDeployment)



* [Set-CMSettingDeployment](Set-CMSettingDeployment)





---


### Examples
#### Example 1: Remove all deployments for a BitLocker management settings object
```PowerShell
Get-CMBlmSetting -Name "My BitLocker settings" | Get-CMSettingDeployment | Remove-CMSettingDeployment
```

#### Example 2: Remove all deployments to a specific collection for a Microsoft Defender Application Control settings object
```PowerShell
Get-CMWdacSetting -Name "My App Control settings" | Get-CMSettingDeployment | Where-Object { $_.CollectionId -eq (Get-CMCollection -Name "All Desktop and Server Clients").CollectionId } | Remove-CMSettingDeployment
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



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





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
Remove-CMSettingDeployment [-CMSettingsDeployment] <SettingsDeployment> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [<CommonParameters>]
```
