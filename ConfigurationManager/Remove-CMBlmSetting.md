Remove-CMBlmSetting
-------------------




### Synopsis
Delete a BitLocker management policy setting object from the site.



---


### Description

Delete a BitLocker management policy setting object from the site. Use Get-CMBlmSetting (Get-CMBlmSetting.md)to get an existing management policy.



---


### Related Links
* [Copy-CMBlmSetting](Copy-CMBlmSetting)



* [Get-CMBlmSetting](Get-CMBlmSetting)



* [New-CMBlmSetting](New-CMBlmSetting)



* [Set-CMBlmSetting](Set-CMBlmSetting)



* [Deploy BitLocker management](Deploy BitLocker management)





---


### Examples
#### Example 1
```PowerShell
Get-CMBlmSetting -Name "My BitLocker setting" | Remove-CMBlmSetting
```



---


### Parameters
#### **CMSettings**

Specify a BitLocker management policy settings object to remove. Use the Get-CMBlmSetting (Get-CMBlmSetting.md)to get this object.






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
Remove-CMBlmSetting [-CMSettings] <CMSettings> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [<CommonParameters>]
```
