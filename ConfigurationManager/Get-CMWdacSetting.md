Get-CMWdacSetting
-----------------




### Synopsis
Get one or all of the Microsoft Defender Application Control policies from the site.



---


### Description

Get one or all of the Microsoft Defender Application Control policies from the site. To create a new policy, use New-CMWdacSetting (New-CMWdacSetting.md).



---


### Related Links
* [Copy-CMWdacSetting](Copy-CMWdacSetting)



* [New-CMWdacSetting](New-CMWdacSetting)



* [Remove-CMWdacSetting](Remove-CMWdacSetting)



* [Set-CMWdacSetting](Set-CMWdacSetting)



* [New-CMSettingDeployment](New-CMSettingDeployment)



* [Windows Defender Application Control management with Configuration Manager](Windows Defender Application Control management with Configuration Manager)





---


### Examples
#### Example 1: Get a Application Control policy by name
```PowerShell
Get-CMWdacSetting -Name "My App Control settings"
```



---


### Parameters
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



#### **Name**

Specify the name of the policy to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.WDAC.CMWdacSettings






---


### Notes




---


### Syntax
```PowerShell
Get-CMWdacSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
