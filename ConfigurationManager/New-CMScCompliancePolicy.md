New-CMScCompliancePolicy
------------------------




### Synopsis
Create a compliance policy to associate an object identifier from a smart card certificate to a BitLocker-protected drive.



---


### Description

Create a compliance policy to associate an object identifier from a smart card certificate to a BitLocker-protected drive. The policy setting applies when you enable BitLocker on a device.



The object identifier is specified in the enhanced key usage (EKU) of a certificate. BitLocker identifies the certificates it can use to authenticate a user certificate to a BitLocker-protected drive. It matches the object identifier in the certificate with the object identifier that you define with this policy.



The default object identifier is `1.3.6.1.4.1.311.67.1.1`.



> [!NOTE] > BitLocker doesn't require that a certificate have an EKU attribute. If the certificate has an EKU, set it to an object identifier (OID) that matches the OID that you configure for BitLocker.



---


### Related Links
* [New-CMBlmSetting](New-CMBlmSetting)



* [BitLocker settings reference](BitLocker settings reference)





---


### Examples
#### Example 1: New default enabled policy
```PowerShell
New-CMScCompliancePolicy -PolicyState Enabled
```

#### Example 2: New enabled policy with a custom OID
```PowerShell
New-CMScCompliancePolicy -PolicyState Enabled -CertificateOid "1.2.3.4.5.6.7.8.9"
```



---


### Parameters
#### **CertificateOid**

Use this parameter to specify a custom OID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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


* `Enabled`: If you enable this policy setting, use the -CertificateOid parameter to specify the object identifier that matches the object identifier in the smart card certificate.


* `Disabled` or `NotConfigured`: If you disable or don't configure this policy setting, it uses the default object identifier.



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
New-CMScCompliancePolicy [-CertificateOid <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-PolicyState {Enabled | Disabled | NotConfigured}] [<CommonParameters>]
```
