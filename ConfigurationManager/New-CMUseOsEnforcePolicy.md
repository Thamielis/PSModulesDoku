New-CMUseOsEnforcePolicy
------------------------




### Synopsis
Create a policy to configure the number of days that users can delay complying with BitLocker policies for their OS drive.



---


### Description

Create a policy to configure the number of days that users can delay complying with BitLocker policies for their OS drive. After the grace period expires, users can't postpone the required action or request an exemption. The grace period begins when BitLocker first detects that the OS drive is noncompliant. This grace period is the same for all users of the computer, regardless of when each user signs in.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New enabled policy with a grace period of seven days
```PowerShell
New-CMUseOsEnforcePolicy -PolicyState Enabled -GracePeriodDays 7
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



#### **GracePeriodDays**

Specify the number of days that the OS drive can be not protected by BitLocker. After this number of days, BitLocker protects the drive and encrypts it.


Specify a value of `0` to immediately enforce this OS drive policy.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, BitLocker enforces the policy on the OS drive, and provides users with grace period that you specify in the -GracePeriodDays parameter.


* `Disabled`, `NotConfigured`: If you disable or don't configure this setting, Configuration Manager doesn't require users to comply with BitLocker policies.



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
New-CMUseOsEnforcePolicy [-DisableWildcardHandling] [-ForceWildcardHandling] [-GracePeriodDays <Int32>] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
