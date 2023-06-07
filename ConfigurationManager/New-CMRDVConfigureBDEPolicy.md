New-CMRDVConfigureBDEPolicy
---------------------------




### Synopsis
Create a policy to control the use of BitLocker on removable data drives.



---


### Description

Create a policy to control the use of BitLocker on removable data drives. This policy setting is applied when you turn on BitLocker.



After BitLocker encrypts a removable data drive, it saves recovery information based on the policy that you set with the New-CMBMSClientConfigureCheckIntervalPolicy (New-CMBMSClientConfigureCheckIntervalPolicy.md)cmdlet.



When you enable BitLocker protection on a removable drive:



- Create a password policy for removable data drives. For more information, see New-CMRDVPassPhrasePolicy (New-CMRDVPassPhrasePolicy.md).



- For higher security, disable the following user and computer group policies under System > Removable Storage Access :



- All Removable storage classes: Deny all access - Removable Disks: Deny write access - Removable Disks: Deny read access



---


### Related Links
* [New-CMBMSClientConfigureCheckIntervalPolicy](New-CMBMSClientConfigureCheckIntervalPolicy)



* [New-CMRDVPassPhrasePolicy](New-CMRDVPassPhrasePolicy)



* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New policy that prevents encryption and decryption of removable drives
```PowerShell
New-CMRDVConfigureBDEPolicy -PolicyState Enabled -PreventEncryption -PreventSuspendAndDecrypt
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


* `Enabled`: When you enable this policy, you control how users can configure BitLocker.


* `NotConfigured`: If you don't configure this policy, users can use BitLocker on removable disk drives.


* `Disabled`: If you disable this policy, users can't use BitLocker on removable disk drives.



Valid Values:

* Enabled
* Disabled
* NotConfigured






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[State]`|false   |named   |False        |



#### **PreventEncryption**

Add this parameter to prevent the user from running the BitLocker setup wizard on a removable data drive.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PreventSuspendAndDecrypt**

Add this parameter to prevent the user from removing BitLocker Drive encryption from the drive. They also can't suspend BitLocker encryption during system maintenance.






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
New-CMRDVConfigureBDEPolicy [-DisableWildcardHandling] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [-PreventEncryption] [-PreventSuspendAndDecrypt] [<CommonParameters>]
```
