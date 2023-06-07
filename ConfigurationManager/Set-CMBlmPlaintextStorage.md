Set-CMBlmPlaintextStorage
-------------------------




### Synopsis
Set a policy to allow the site to store BitLocker recovery information in plain text.



---


### Description

Set a policy to allow the site to store BitLocker recovery information in plain text. Without a BitLocker management encryption certificate for SQL Server, Configuration Manager stores the key recovery information in plain text. For more information, see Encrypt recovery data (/mem/configmgr/protect/deploy-use/bitlocker/encrypt-recovery-data).



To add this policy to a settings object, use the New-CMBlmSetting (New-CMBlmSetting.md) or [Set-CMBlmSetting](Set-CMBlmSetting.md)cmdlets.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [Set-CMBlmSetting](Set-CMBlmSetting)



* [Encrypt recovery data](Encrypt recovery data)



* [BitLocker settings reference](BitLocker settings reference)





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





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMBlmPlaintextStorage [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
