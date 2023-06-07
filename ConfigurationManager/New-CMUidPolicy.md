New-CMUidPolicy
---------------




### Synopsis
Create a policy to associate unique organizational identifiers to a new drive that is enabled with BitLocker.



---


### Description

Use this cmdlet to create a policy to associate unique organizational identifiers (OID) to a new drive that is enabled with BitLocker. These identifiers are stored as the identification field and allowed identification field. The identification field allows you to associate a unique organizational identifier to BitLocker-protected drives. This identifier is automatically added to new BitLocker-protected drives. You can update it on existing BitLocker-protected drives using the Manage-BDE command-line tool.



An identification field is required for management of certificate-based data recovery agents on BitLocker-protected drives and for potential updates to the BitLocker To Go Reader. BitLocker will only manage and update data recovery agents when the identification field on the drive matches the value configured in the identification field. In a similar manner, BitLocker will only update the BitLocker To Go Reader when the identification field on the drive matches the value configured for the identification field.



The allowed identification field is used in combination with the New-CMRDVDenyWriteAccessPolicy (New-CMRDVDenyWriteAccessPolicy.md)cmdlet to help control the use of removable drives in your organization. It's a comma-separated list of identification fields from your organization or other external organizations.



When a BitLocker-protected drive is mounted on another BitLocker-enabled computer, the identification field and allowed identification field will be used to determine whether the drive is from an outside organization.



> [!NOTE] > Identification fields are required for management of certificate-based data recovery agents on BitLocker-protected drives. BitLocker only manages and updates certificate-based data recovery agents when the identification field is present on a drive and is identical to the value configured on the computer. The identification field can be any value of 260 characters or fewer.



---


### Related Links
* [New-CMRDVDenyWriteAccessPolicy](New-CMRDVDenyWriteAccessPolicy)



* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New enabled policy with custom OIDs
```PowerShell
New-CMUidPolicy -PolicyState Enabled -BitLockerIdOid "1.2.840.113549.1.1.1" -AllowedBitLockerIdOid "1.3.6.1.4.1.311.20.2"
```



---


### Parameters
#### **AllowedBitLockerIdOid**

Specify a comma-separated list of allowed identifiers from your organization or other external organizations.






|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[Oid]`|false   |named   |False        |



#### **BitLockerIdOid**

Specify the BitLocker identifier.






|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[Oid]`|false   |named   |False        |



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


* `Enabled`: If you enable this policy setting, you can configure the identification field on the BitLocker-protected drive and any allowed identification field used by your organization.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy setting, the identification field isn't required.



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
New-CMUidPolicy [-AllowedBitLockerIdOid <Oid>] [-BitLockerIdOid <Oid>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
