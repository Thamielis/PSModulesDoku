Import-CMCertificate
--------------------




### Synopsis
Imports a certificate.



---


### Description

The Import-CMCertificate cmdlet imports a public key infrastructure (PKI) certificate to Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Update-CMCertificate](Update-CMCertificate)



* [Block-CMCertificate](Block-CMCertificate)



* [Unblock-CMCertificate](Unblock-CMCertificate)





---


### Examples
#### Example 1: Import a certificate
```PowerShell
PS XYZ:\>Import-CMCertificate -Path "\\Contoso01\CM\Certficates\BaseCert.txt"
```
This command imports the PKI certificate from the file named BaseCert.


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



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

Specifies a certification path.






|Type      |Required|Position|PipelineInput|Aliases                                                     |
|----------|--------|--------|-------------|------------------------------------------------------------|
|`[String]`|true    |0       |False        |CertificatePath<br/>FileName<br/>FilePath<br/>ImportFilePath|



#### **X509Certificate**








|Type               |Required|Position|PipelineInput |
|-------------------|--------|--------|--------------|
|`[X509Certificate]`|true    |0       |True (ByValue)|



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
System.Security.Cryptography.X509Certificates.X509Certificate





---


### Outputs
* IResultObject[]#SMS_ISVProxyCertificateInfo


* IResultObject#SMS_ISVProxyCertificateInfo






---


### Notes




---


### Syntax
```PowerShell
Import-CMCertificate [-Path] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Import-CMCertificate [-X509Certificate] <X509Certificate> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
