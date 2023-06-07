New-CMFDVDenyWriteAccessPolicy
------------------------------




### Synopsis
Create a new policy to determine whether BitLocker protection is required for fixed data drives to be writable on a computer.



---


### Description

Create a new policy to determine whether BitLocker protection is required for fixed data drives to be writable on a computer.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New default enabled policy
```PowerShell
New-CMFDVDenyWriteAccessPolicy -PolicyState Enabled
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


* `Enabled`: If you enable this policy setting, Windows mounts all fixed data drives that BitLocker doesn't protect as read-only. If BitLocker protects the drive, Windows mounts it  with read and write access.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy setting, Windows mounts all fixed data drives on the computer with read and write access.



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
New-CMFDVDenyWriteAccessPolicy [-DisableWildcardHandling] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
