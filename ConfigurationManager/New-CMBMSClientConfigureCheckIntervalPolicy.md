New-CMBMSClientConfigureCheckIntervalPolicy
-------------------------------------------




### Synopsis
Create a policy to manage the key recovery service backup of BitLocker Drive Encryption recovery information.



---


### Description

Create a policy to manage the key recovery service backup of BitLocker Drive Encryption recovery information. This backup provides an administrative method of recovering data encrypted by BitLocker to prevent data loss because of lack of key information.



BitLocker recovery information includes the recovery password and some unique identifier data. You can also select to include a package that contains a BitLocker protected drive's encryption key. This key package is secured by one or more recovery passwords. The package may help with specialized recovery when the disk is damaged or corrupted.



This policy manages how often the client checks the BitLocker protection policies and status on the device. You can also manage the compliance and status information to save to the BitLocker report server. This behavior provides an administrative method of generating a compliance and status report.



---


### Related Links
* [New-CMRDVConfigureBDEPolicy](New-CMRDVConfigureBDEPolicy)



* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New policy with a 45-minute client check period and only password escrow
```PowerShell
New-CMBMSClientConfigureCheckIntervalPolicy -PolicyState Enabled -ClientWakeupFrequencyMinutes 45 -KeyRecoveryOption PasswordOnly
```

#### Example 2: New policy with a daily client check period and escrows a recovery package
```PowerShell
New-CMBMSClientConfigureCheckIntervalPolicy -PolicyState Enabled -ClientWakeupFrequencyMinutes 1440 -KeyRecoveryOption PasswordAndPackage
```



---


### Parameters
#### **ClientWakeupFrequencyMinutes**

Set this parameter to manage the frequency of the compliance and status information that the client reports to the BitLocker report service. The frequency is every 1 minute to 2880 minutes (48 hours). The default for the client to check status is 90 minutes.


Frequency values smaller than the default will increase network and server usage. Smaller values can limit the number of clients that the server can process.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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



#### **KeyRecoveryOption**

BitLocker recovery information includes the recovery password and some unique identifier data. You can also select to include a package that contains a BitLocker protected drive's encryption key. This key package is secured by one or more recovery passwords. The package may help with specialized recovery when the disk is damaged or corrupted.



Valid Values:

* PasswordAndPackage
* PasswordOnly






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[KeyRecoveryOption]`|false   |named   |False        |



#### **PolicyState**

Use this parameter to configure the policy.


* `Enabled`: If you enable this policy, key recovery info is automatically and silently backed up to the configured key recovery server location. A status report is automatically and silently sent to the configured report server location.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy, the client doesn't save key recovery or status report information.



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
New-CMBMSClientConfigureCheckIntervalPolicy [-ClientWakeupFrequencyMinutes <Int32>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-KeyRecoveryOption {PasswordAndPackage | PasswordOnly}] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
