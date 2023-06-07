New-CMBLEncryptionMethodWithXts
-------------------------------




### Synopsis
Create a policy to configure the algorithm and cipher strength used by BitLocker Drive Encryption on Windows 10 devices.



---


### Description

Create a policy to configure the algorithm and cipher strength used by BitLocker Drive Encryption on Windows 10 devices. This policy is applied when you turn on BitLocker. If the drive is already encrypted, or if encryption is in progress, changing the encryption method has no effect.



For Windows 8.1 devices, use the New-CMBLEncryptionMethodPolicy (New-CMBLEncryptionMethodPolicy.md)cmdlet.



---


### Related Links
* [New-CMBLEncryptionMethodPolicy](New-CMBLEncryptionMethodPolicy)



* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New disabled policy
```PowerShell
New-CMBLEncryptionMethodPolicy -PolicyState Enabled -EncryptionMethod AES256
New-CMBLEncryptionMethodWithXts -PolicyState Disabled
```

#### Example 2: New enabled policy with XTS-CBC 128-bit encryption
```PowerShell
New-CMBLEncryptionMethodWithXts -PolicyState Enabled -OSDriveEncryptionMethod AesCbc128 -FixedDriveEncryptionMethod AesCbc128 -RemovableDriveEncryptionMethod AesCbc128
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FixedDriveEncryptionMethod**

Specify an encryption method for fixed data drives.



Valid Values:

* AesXts128
* AesXts256
* AesCbc128
* AesCbc256






|Type                          |Required|Position|PipelineInput|
|------------------------------|--------|--------|-------------|
|`[WindowsTenEncryptionMethod]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **OSDriveEncryptionMethod**

Specify an encryption method for the OS drive.



Valid Values:

* AesXts128
* AesXts256
* AesCbc128
* AesCbc256






|Type                          |Required|Position|PipelineInput|
|------------------------------|--------|--------|-------------|
|`[WindowsTenEncryptionMethod]`|false   |named   |False        |



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, separately configure an encryption algorithm and key cipher strength for fixed data drives, OS drives, and removable data drives. For fixed and OS drives, the XTS-AES algorithm is recommended. If you'll use a removable drive in a Windows 8.1 device, use AES-CBC 128-bit or AES-CBC 256-bit.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy, BitLocker uses AES with the same bit strength as a policy that you specify with the New-CMBLEncryptionMethodPolicy (New-CMBLEncryptionMethodPolicy.md)cmdlet. If you don't enable that policy, BitLocker uses the default encryption method of XTS-AES 128-bit.



Valid Values:

* Enabled
* Disabled
* NotConfigured






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[State]`|false   |named   |False        |



#### **RemovableDriveEncryptionMethod**

Specify an encryption method for removable drives.



Valid Values:

* AesXts128
* AesXts256
* AesCbc128
* AesCbc256






|Type                          |Required|Position|PipelineInput|
|------------------------------|--------|--------|-------------|
|`[WindowsTenEncryptionMethod]`|false   |named   |False        |





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
New-CMBLEncryptionMethodWithXts [-DisableWildcardHandling] [-FixedDriveEncryptionMethod {AesXts128 | AesXts256 | AesCbc128 | AesCbc256}] [-ForceWildcardHandling] [-OSDriveEncryptionMethod {AesXts128 | AesXts256 | AesCbc128 | AesCbc256}] [-PolicyState {Enabled | Disabled | NotConfigured}] [-RemovableDriveEncryptionMethod {AesXts128 | AesXts256 | AesCbc128 | AesCbc256}] [<CommonParameters>]
```
