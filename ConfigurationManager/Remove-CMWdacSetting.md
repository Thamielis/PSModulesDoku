Remove-CMWdacSetting
--------------------




### Synopsis
Delete a Microsoft Defender Application Control policy from the site.



---


### Description

Delete a Microsoft Defender Application Control policy from the site. Use Get-CMWdacSetting (Get-CMWdacSetting.md)to get an existing policy object.



---


### Related Links
* [Copy-CMWdacSetting](Copy-CMWdacSetting)



* [Get-CMWdacSetting](Get-CMWdacSetting)



* [New-CMWdacSetting](New-CMWdacSetting)



* [Set-CMWdacSetting](Set-CMWdacSetting)



* [Windows Defender Application Control management with Configuration Manager](Windows Defender Application Control management with Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Get-CMWdacSetting -Name "My App Control setting" | Remove-CMWdacSetting
```



---


### Parameters
#### **CMSettings**

Specify a Microsoft Defender Application Control policy object to remove. Use the Get-CMWdacSetting (Get-CMWdacSetting.md)to get this object.






|Type          |Required|Position|PipelineInput |
|--------------|--------|--------|--------------|
|`[CMSettings]`|true    |1       |True (ByValue)|



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
Microsoft.ConfigurationManagement.PowerShell.Cmdlets.EP.SimplifiedSettings.CMSettings





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMWdacSetting [-CMSettings] <CMSettings> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [<CommonParameters>]
```
