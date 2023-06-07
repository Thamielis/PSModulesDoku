New-CMUseFddEnforcePolicy
-------------------------




### Synopsis
Create a policy to configure the number of days that fixed drives can remain noncompliant until they are forced to comply with BitLocker policies.



---


### Description

Create a policy to configure the number of days that fixed drives can remain noncompliant until they are forced to comply with BitLocker policies. After the grace period, users can't postpone the required action or request an exemption. The grace period starts when BitLocker determines the fixed data drive is noncompliant. BitLocker doesn't enforce the fixed data drive policy until the OS drive is compliant.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New enabled policy with grace period set to seven days
```PowerShell
New-CMUseFddEnforcePolicy -PolicyState Enabled -GracePeriodDays 7
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

Specify the number of days that a fixed data drive can be not protected by BitLocker. After this number of days, BitLocker protects the drive and encrypts it.


Specify a value of `0` to immediately enforce this fixed data drive policy after the OS drive becomes compliant.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, BitLocker enforces the policy on fixed data drives, and provides users with grace period that you specify in the -GracePeriodDays parameter.


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
New-CMUseFddEnforcePolicy [-DisableWildcardHandling] [-ForceWildcardHandling] [-GracePeriodDays <Int32>] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
