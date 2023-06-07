Copy-CMBlmSetting
-----------------




### Synopsis
Make a copy of a BitLocker management policy settings object.



---


### Description

This cmdlet makes a copy of a BitLocker Management policy settings object. All existing policies are included. Use the Get-CMBlmSetting (Get-CMBlmSetting.md)to get this object.



---


### Related Links
* [Get-CMBlmSetting](Get-CMBlmSetting)



* [New-CMBlmSetting](New-CMBlmSetting)



* [Remove-CMBlmSetting](Remove-CMBlmSetting)



* [Set-CMBlmSetting](Set-CMBlmSetting)





---


### Examples
#### Example 1: Copy an existing policy object
```PowerShell
Get-CMBlmSetting -Name "My BitLocker settings" | Copy-CMBlmSetting -Name "New BitLocker settings"
```



---


### Parameters
#### **BlmSettings**

Specify a BitLocker management policy settings object to copy. Use the Get-CMBlmSetting (Get-CMBlmSetting.md)to get this object.






|Type           |Required|Position|PipelineInput |
|---------------|--------|--------|--------------|
|`[BlmSettings]`|true    |1       |True (ByValue)|



#### **Description**

Specify a description for the new BitLocker management policy object.






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



#### **Name**

Specify a name for the new BitLocker management policy object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.BitLockerManagement.BlmSettings





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.BitLockerManagement.BlmSettings






---


### Notes




---


### Syntax
```PowerShell
Copy-CMBlmSetting [-BlmSettings] <BlmSettings> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
