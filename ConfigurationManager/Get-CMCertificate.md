Get-CMCertificate
-----------------




### Synopsis
Gets a certificate.



---


### Description

The Get-CMCertificate cmdlet gets a certificate.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Import-CMCertificate](Import-CMCertificate)



* [Update-CMCertificate](Update-CMCertificate)



* [Block-CMCertificate](Block-CMCertificate)



* [Unblock-CMCertificate](Unblock-CMCertificate)





---


### Examples
#### Example 1: Get all certificates
```PowerShell
PS ABC:\> Get-CMCertificate
```
This command gets all certificates.
#### Example 2: Get a certificate by ID and thumbprint
```PowerShell
PS ABC:\> Get-CMCertificate -Id "{4680a1bb-ae51-4bdf-8f27-979eb49e444e}" -Thumbprint e1c2fff14282b61f79f78fbfca6721f0517ab767 -CertificateType DistributionPoint -KeyType SelfSigned
```
This command gets the self-signed distribution point certificate with the specified ID and thumbprint.


---


### Parameters
#### **CertificateType**

Specifies the certificate type. Valid values are:


* BootMedia


* DistributionPoint


* IsvProxy



Valid Values:

* BootMedia
* DistributionPoint
* IsvProxy






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[CertificateType]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Indicates that the cmdlet does not automatically refresh lazy properties.


Lazy properties contain values that are relatively inefficient to retrieve which can cause additional network traffic and decrease cmdlet performance. If lazy properties are not used, this parameter should be specified.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the ID of a certificate.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |SmsId  |



#### **KeyType**

Specifies the key type of the certificate. Valid values are:


* SelfSigned


* Issued



Valid Values:

* SelfSigned
* Issued






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[KeyType]`|false   |named   |False        |



#### **Thumbprint**

Specifies the thumbprint of the certificate.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_Certificate


* IResultObject#SMS_Certificate






---


### Notes




---


### Syntax
```PowerShell
Get-CMCertificate [-CertificateType {BootMedia | DistributionPoint | IsvProxy}] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Id <String>] [-KeyType {SelfSigned | Issued}] [-Thumbprint <String>] [<CommonParameters>]
```
