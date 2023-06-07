Get-CMBlmSetting
----------------




### Synopsis
Get one or all the BitLocker management policies from the site.



---


### Description

Get one or all the BitLocker management policies from the site. Use New-CMBlmSetting (New-CMBlmSetting.md)to create a new management policy.



---


### Related Links
* [Copy-CMBlmSetting](Copy-CMBlmSetting)



* [New-CMBlmSetting](New-CMBlmSetting)



* [Remove-CMBlmSetting](Remove-CMBlmSetting)



* [Set-CMBlmSetting](Set-CMBlmSetting)



* [New-CMSettingDeployment](New-CMSettingDeployment)



* [Deploy BitLocker management](Deploy BitLocker management)





---


### Examples
#### Example 1: Get all the BitLocker management policies and filter by description
```PowerShell
Get-CMBlmSetting | Where-Object { $_.Description -eq "Unique Description" }
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
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.BitLockerManagement.BlmSettings






---


### Notes




---


### Syntax
```PowerShell
Get-CMBlmSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
