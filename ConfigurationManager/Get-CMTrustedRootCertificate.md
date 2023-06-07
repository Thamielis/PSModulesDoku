Get-CMTrustedRootCertificate
----------------------------




### Synopsis
Gets a trusted root certificate for Configuration Manager.



---


### Description

The Get-CMTrustedRootCertificate cmdlet gets a trusted root certificate for Configuration Manager. For native mode communication, Configuration Manager authenticates, encrypts, and signs communications based on public key infrastructure (PKI) keys that depend on trusted root certificate. Devices that communicate by using certificates must have a root certificate in common. Devices in your Configuration Manager hierarchy might have different root certificates. If so, install all necessary trusted root certificates.



Computers that run the Windows operating system, as well as many other devices, rely on some well-known third-party root certificates. If you deploy your own PKI, install the required root certificate.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Get a trusted root certificate
```PowerShell
PS XYZ:\> Get-CMTrustedRootCertificate -CertificationAuthorityServerName "ContosoCA.Contoso.com"
```
This command gets a trusted root certificate from the internal server named ContosoCA.Contoso.com.


---


### Parameters
#### **CAServerName**








|Type      |Required|Position|PipelineInput|Aliases                         |
|----------|--------|--------|-------------|--------------------------------|
|`[String]`|false   |named   |False        |CertificationAuthorityServerName|



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





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Get-CMTrustedRootCertificate [-CAServerName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
