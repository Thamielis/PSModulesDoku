Copy-CMWdacSetting
------------------




### Synopsis
Make a copy of a Microsoft Defender Application Control policy object.



---


### Description

This cmdlet makes a copy of a Microsoft Defender Application Control policy object. All existing policies are included. Use the Get-CMWdacSetting (Get-CMWdacSetting.md)to get this object.



---


### Related Links
* [Get-CMWdacSetting](Get-CMWdacSetting)



* [New-CMWdacSetting](New-CMWdacSetting)



* [Remove-CMWdacSetting](Remove-CMWdacSetting)



* [Set-CMWdacSetting](Set-CMWdacSetting)





---


### Examples
#### Example 1: Copy an existing policy object
```PowerShell
Get-CMWdacSetting -Name "My App Control settings" | Copy-CMWdacSetting -Name "New App Control settings"
```



---


### Parameters
#### **Description**

Specify a description for the new Microsoft Defender Application Control policy object.






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

Specify a name for the new Microsoft Defender Application Control policy object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **WdacSettings**

Specify a Microsoft Defender Application Control policy object to copy. Use the Get-CMWdacSetting (Get-CMWdacSetting.md)to get this object.






|Type              |Required|Position|PipelineInput |
|------------------|--------|--------|--------------|
|`[CMWdacSettings]`|true    |1       |True (ByValue)|





---


### Inputs
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.WDAC.CMWdacSettings





---


### Outputs
* Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.WDAC.CMWdacSettings






---


### Notes




---


### Syntax
```PowerShell
Copy-CMWdacSetting [-WdacSettings] <CMWdacSettings> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
