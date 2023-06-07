New-CMBLEncryptionMethodPolicy
------------------------------




### Synopsis
Create a policy to configure the algorithm and cipher strength used by BitLocker Drive Encryption on Windows 8.1 devices.



---


### Description

Create a policy to configure the algorithm and cipher strength used by BitLocker Drive Encryption on Windows 8.1 devices. This policy is applied when you turn on BitLocker. If the drive is already encrypted, or if encryption is in progress, changing the encryption method has no effect.



For Windows 10 devices, use the New-CMBLEncryptionMethodWithXts (New-CMBLEncryptionMethodWithXts.md)cmdlet.



---


### Related Links
* [New-CMBLEncryptionMethodWithXts](New-CMBLEncryptionMethodWithXts)



* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New enabled policy with AES 256-bit encryption
```PowerShell
New-CMBLEncryptionMethodPolicy -PolicyState Enabled -EncryptionMethod AES256
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EncryptionMethod**

Specify one of the encryption methods for BitLocker to use when it encrypts drives. AES 128-bit (`Aes128`) is the default value.



Valid Values:

* Aes128Diffuser
* Aes256Diffuser
* Aes128
* Aes256






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[EncryptionMethod]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, use the -EncryptionMethod parameter to specify an encryption algorithm and key cipher strength. BitLocker uses these settings to encrypt drives.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy, BitLocker uses the default encryption method of AES 128-bit.



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
New-CMBLEncryptionMethodPolicy [-DisableWildcardHandling] [-EncryptionMethod {Aes128Diffuser | Aes256Diffuser | Aes128 | Aes256}] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
