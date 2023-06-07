New-CMBMSOSDEncryptionPolicy
----------------------------




### Synopsis
Create a policy to manage whether to encrypt the OS drive with BitLocker.



---


### Description

Use this cmdlet to create a policy to manage whether to encrypt the OS drive with BitLocker.



If you want to use BitLocker on a computer without a Trusted Platform Module (TPM) (/windows/security/information-protection/tpm/trusted-platform-module-top-node), don't use the -RequireTpm parameter. In this mode, BitLocker requires a password when the device starts up. If you forget the password, use a BitLocker recovery option to access the drive.



On a computer with a compatible TPM, BitLocker can use two authentication methods when the device starts up. This behavior provides added protection for encrypted data. When the computer starts, it can use only the TPM for authentication, or it can also require the entry of a personal identification number (PIN).



> [!TIP] > For higher security, when you enable devices with TPM + PIN protector, consider disabling the following group policy settings in System > Power Management > Sleep Settings : > > - Allow Standby States (S1-S3) When Sleeping (Plugged In) > > - Allow Standby States (S1-S3) When Sleeping (On Battery)



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: Create a new policy that requires TPM with PIN
```PowerShell
New-CMBMSOSDEncryptionPolicy -PolicyState Enabled -RequireTpm -MinimumPinLength 16 -Protector TpmAndPin
```

#### Example 2: Create a new policy for TPM only
```PowerShell
New-CMBMSOSDEncryptionPolicy -PolicyState Enabled -Protector TpmOnly
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



#### **MinimumPinLength**

If you require a PIN, this value is the shortest length the user can specify. The user enters this PIN when the computer boots to unlock the drive. By default, the minimum PIN length is `4`. Set a value from `4` to `20`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|false   |named   |False        |



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, the user has to put the OS drive under BitLocker protection, and it encrypts the drive.


* `Disabled`: If you disable this policy, the user can't put the OS drive under BitLocker protection. If you apply this policy after the OS drive is encrypted, BitLocker decrypts the drive.


* `NotConfigured`: If you don't configure this policy, then BitLocker isn't required on the OS drive.



Valid Values:

* Enabled
* Disabled
* NotConfigured






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[State]`|false   |named   |False        |



#### **Protector**

Use this parameter to specify a protector for the OS drive:


* `TpmOnly`: Only use the TPM as a protector


* `TpmAndPin`: Use a PIN with the TPM



Valid Values:

* TpmOnly
* TpmAndPin






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TpmProtector]`|false   |named   |False        |



#### **RequireTpm**

Add this parameter to configure the policy to require the device to have a compatible TPM.






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
New-CMBMSOSDEncryptionPolicy [-DisableWildcardHandling] [-ForceWildcardHandling] [-MinimumPinLength <UInt32>] [-PolicyState {Enabled | Disabled | NotConfigured}] [-Protector {TpmOnly | TpmAndPin}] [-RequireTpm] [<CommonParameters>]
```
