Get-CMSettingDeployment
-----------------------




### Synopsis
Get all of the deployments for a settings policy object.



---


### Description

Get all of the deployments for a settings policy object. For example, a BitLocker management policy or a Microsoft Defender Application Control policy. Use the New-CMSettingDeployment (New-CMSettingDeployment.md)to deploy a policy object.



---


### Related Links
* [New-CMSettingDeployment](New-CMSettingDeployment)



* [Remove-CMSettingDeployment](Remove-CMSettingDeployment)



* [Set-CMSettingDeployment](Set-CMSettingDeployment)





---


### Examples
#### Example 1: Get all deployments for a BitLocker management setting
```PowerShell
Get-CMBlmSetting -Name "My BitLocker setting" | Get-CMSettingDeployment
```

#### Example 2: Get all deployments for a Microsoft Defender Application Control setting
```PowerShell
Get-CMWdacSetting -Name "My App Control setting" | Get-CMSettingDeployment
```



---


### Parameters
#### **CMSetting**

Specify a settings object to get its deployments.


* For BitLocker management, use the Get-CMBlmSetting (Get-CMBlmSetting.md)cmdlet. - For Microsoft Defender Application Control, use the Get-CMWdacSetting (Get-CMWdacSetting.md)cmdlet.






|Type          |Required|Position|PipelineInput |
|--------------|--------|--------|--------------|
|`[CMSettings]`|true    |1       |True (ByValue)|



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
Get-CMSettingDeployment [-CMSetting] <CMSettings> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
