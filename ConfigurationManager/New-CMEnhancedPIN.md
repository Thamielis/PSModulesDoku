New-CMEnhancedPIN
-----------------




### Synopsis
Create a policy to configure whether BitLocker can use enhanced startup PINs.



---


### Description

Create a policy to configure whether BitLocker can use enhanced startup PINs. Enhanced startup PINs permit the use of characters including uppercase and lowercase letters, symbols, numbers, and spaces. This policy setting is applied when you turn on BitLocker.



Not all computers support enhanced PINs in the pre-boot environment. Before you enable this policy, evaluate if your devices are compatible with it. Use the -RequireAsciiOnlyPin parameter to help make enhanced PINs more compatible with computers that limit the type or number of characters that you can enter in the pre-boot environment.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New default enabled policy
```PowerShell
New-CMEnhancedPIN -PolicyState Enabled
```

#### Example 2: New enabled policy with ASCII-only PIN
```PowerShell
New-CMEnhancedPIN -PolicyState Enabled -RequireAsciiOnlyPin
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


* `Enabled`: If you enable this policy, all new BitLocker startup PINs will be enhanced PINs.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy, BitLocker won't use enhanced PINs.



Valid Values:

* Enabled
* Disabled
* NotConfigured






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[State]`|false   |named   |False        |



#### **RequireAsciiOnlyPin**

Use this parameter to help make enhanced PINs more compatible with computers that limit the type or number of characters that you can enter in the pre-boot environment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.AdminConsole.BitlockerManagement.PolicyObject






---


### Notes




---


### Syntax
```PowerShell
New-CMEnhancedPIN [-DisableWildcardHandling] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [-RequireAsciiOnlyPin] [<CommonParameters>]
```
