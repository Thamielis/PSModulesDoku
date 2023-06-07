New-CMRDVPassPhrasePolicy
-------------------------




### Synopsis
Create a policy to specify whether a password is required to unlock BitLocker-protected removable data drives.



---


### Description

Create a policy to specify whether a password is required to unlock BitLocker-protected removable data drives. If you allow a password, you can require it, enforce complexity requirements, and configure a minimum length. For these complexity requirement settings to be effective, also enable the group policy setting Password must meet complexity requirements in Computer Configuration > Windows Settings > Security Settings > Account Policies > Password Policy .



> [!NOTE] > Windows enforces these settings when you enable BitLocker, not when it unlocks a volume. BitLocker allows a user to unlock a drive with any of the available protectors. > > You can't use passwords if you also enable Windows to use FIPS-compliant algorithms for encryption, hashing, and signing.



---


### Related Links
* [New-CMRDVConfigureBDEPolicy](New-CMRDVConfigureBDEPolicy)



* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New enabled policy that sets complexity and minimum length
```PowerShell
New-CMRDVPassPhrasePolicy -PolicyState Enabled -PasswordComplexity Require -MinimumLength 10
```

#### Example 2: New policy that requires a password
```PowerShell
New-CMRDVPassPhrasePolicy -PolicyState Enabled -PasswordComplexity Allow -MinimumLength 12 -RequirePassword
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



#### **MinimumLength**

Passwords must be at least `8` characters. To configure a greater minimum length for the password, use this parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt64]`|false   |named   |False        |



#### **PasswordComplexity**

Use this parameter to configure password complexity for removable data drives. To enforce complexity requirements on the password, set the value to `Require`.


* `Require`: When you enable BitLocker, a connection to a domain controller is necessary to validate the complexity of the password.


* `Allow`: The device tries to connect to a domain controller to validate the complexity. If it can't communicate with a domain controller, it still accepts the password whatever the actual complexity. BitLocker encrypts the drive using that password as a protector.


* `Prohibit`: The client doesn't connect to a domain controller to validate the password complexity.



Valid Values:

* Allow
* Require
* Prohibit






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[Dispensation]`|false   |named   |False        |



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, users can configure a password that meets the requirements you define. To enforce complexity requirements on the password, use `-PasswordComplexity Require`.


* `Disabled`: If you disable this policy, the user can't use a password.


* `NotConfigured`: If you don't configure this policy, BitLocker supports passwords for removable data drives with the default settings. The default settings don't include password complexity requirements and require only eight characters.



Valid Values:

* Enabled
* Disabled
* NotConfigured






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[State]`|false   |named   |False        |



#### **RequirePassword**

Add this parameter to require a password to unlock a BitLocker-protected removable data drive.






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
New-CMRDVPassPhrasePolicy [-DisableWildcardHandling] [-ForceWildcardHandling] [-MinimumLength <UInt64>] [-PasswordComplexity {Allow | Require | Prohibit}] [-PolicyState {Enabled | Disabled | NotConfigured}] [-RequirePassword] [<CommonParameters>]
```
