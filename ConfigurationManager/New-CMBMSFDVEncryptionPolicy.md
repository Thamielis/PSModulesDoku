New-CMBMSFDVEncryptionPolicy
----------------------------




### Synopsis
Create a policy to manage whether to use BitLocker encryption on fixed data drives.



---


### Description

Create a policy to manage whether to use BitLocker encryption on fixed data drives.



When you enable this policy, also create a password policy for fixed data drives. The only exception is if you allow or require the use of auto-unlock for fixed data drives. For more information, see New-CMFDVPassPhrasePolicy (New-CMFDVPassPhrasePolicy.md).



If you require the use of auto-unlock for fixed data drives, encrypt the OS volume too.



---


### Related Links
* [New-CMFDVPassPhrasePolicy](New-CMFDVPassPhrasePolicy)



* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New enabled policy that prohibits auto-unlock
```PowerShell
New-CMBMSFDVEncryptionPolicy -PolicyState Enabled -AutoUnlock Prohibit
```



---


### Parameters
#### **AutoUnlock**

Allow, require, or prohibit BitLocker to automatically unlock any encrypted data drive. To use auto-unlock, also require BitLocker to encrypt the OS drive.



Valid Values:

* Allow
* Require
* Prohibit






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[Dispensation]`|false   |named   |False        |



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


* `Enabled`: If you enable this policy, the user has to put all fixed data drives under the BitLocker protection, and BitLocker encrypts the drives.


* `Disabled`: If you disable this policy, the user can't put fixed data drives under BitLocker protection. If you disable this policy after BitLocker encrypts fixed data drives, BitLocker decrypts the fixed data drives.


* `NotConfigured`: If you don't configure this policy, BitLocker doesn't require users to put fixed data drives under protection.



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
New-CMBMSFDVEncryptionPolicy [-AutoUnlock {Allow | Require | Prohibit}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
