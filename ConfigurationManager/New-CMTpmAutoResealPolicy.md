New-CMTpmAutoResealPolicy
-------------------------




### Synopsis
Create a policy to control whether Windows refreshes platform validation data when it starts after BitLocker recovery.



---


### Description

Create a policy to control whether Windows refreshes platform validation data when it starts after BitLocker recovery.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New default enabled policy
```PowerShell
New-CMTpmAutoResealPolicy -PolicyState Enabled
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


* `Enabled` or `NotConfigured`: If you enable or don't configure this policy, Windows refreshes platform validation data when it starts after BitLocker recovery.


* `Disabled`: If you disable this policy, Windows doesn't refresh platform validation data when it starts after BitLocker recovery.



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
* Microsoft.ConfigurationManagement.AdminConsole.BitlockerManagement.PolicyObject






---


### Notes




---


### Syntax
```PowerShell
New-CMTpmAutoResealPolicy [-DisableWildcardHandling] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
