New-CMRDVDenyWriteAccessPolicy
------------------------------




### Synopsis
Create a policy to configure whether BitLocker protection is required for removable data drives to be writable on a computer.



---


### Description

Create a policy to configure whether BitLocker protection is required for removable data drives to be writable on a computer.



---


### Related Links
* [New-CMUidPolicy](New-CMUidPolicy)



* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New default enabled policy
```PowerShell
New-CMRDVDenyWriteAccessPolicy -PolicyState Enabled
```



---


### Parameters
#### **AllowWriteAccessToExternalOrganizationDrives**

Add this parameter to allow a removable data drive to be writeable without checking identification fields.


If you don't add this parameter, only drives with identification fields matching the computer's identification fields are writeable. When the system accesses a removable data drive, Windows checks for a valid identification field and allowed identification fields. These fields are defined by the "Provide the unique identifiers for your organization" policy setting. For more information, see New-CMUidPolicy (New-CMUidPolicy.md).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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


* `Enabled`: If you enable this policy setting, Windows mounts all removable data drives that BitLocker doesn't protect as read-only. If BitLocker protects the drive, Windows mounts it with read and write access.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy setting, Windows mounts all removable data drives on the computer with read and write access.



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
New-CMRDVDenyWriteAccessPolicy [-AllowWriteAccessToExternalOrganizationDrives] [-DisableWildcardHandling] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
