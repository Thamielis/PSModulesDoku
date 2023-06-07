New-CMNoOverwritePolicy
-----------------------




### Synopsis
Create a policy to control computer restart performance at the risk of exposing BitLocker secrets.



---


### Description

Create a policy to control computer restart performance at the risk of exposing BitLocker secrets. BitLocker secrets include key material used to encrypt data. This policy applies only when you enable BitLocker protection.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New default enabled policy
```PowerShell
New-CMNoOverwritePolicy -PolicyState NotConfigured
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



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, memory isn't overwritten when the computer restarts. Preventing memory overwrite may improve restart performance, but it increases the risk of exposing BitLocker secrets.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy, BitLocker secrets are removed from memory when the computer restarts.



Valid Values:

* Enabled
* Disabled
* NotConfigured






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[State]`|false   |named   |False        |





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
New-CMNoOverwritePolicy [-DisableWildcardHandling] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
