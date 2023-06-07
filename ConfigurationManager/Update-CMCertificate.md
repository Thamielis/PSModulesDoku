Update-CMCertificate
--------------------




### Synopsis
Updates a certificate.



---


### Description

The Update-CMCertificate cmdlet updates a public key infrastructure (PKI) certificate that Configuration Manager uses.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Block-CMCertificate](Block-CMCertificate)



* [Unblock-CMCertificate](Unblock-CMCertificate)



* [Import-CMCertificate](Import-CMCertificate)





---


### Examples
#### Example 1: Update a certificate
```PowerShell
PS XYZ:\>Update-CMCertificate -Id "ManagementCertificate" -Path "C:\Certificates\Management.pfx"
```
This command modifies the certificate path for the certificate with the ID ManagementCertificate. In this example, the path is changed to C:\Certificates\Management.pfx.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






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
|`[String]`|true    |named   |False        |SmsId  |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Certificate|



#### **Path**

Specifies a certification path.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **X509Certificate**








|Type               |Required|Position|PipelineInput |
|-------------------|--------|--------|--------------|
|`[X509Certificate]`|true    |named   |True (ByValue)|



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject



System.Security.Cryptography.X509Certificates.X509Certificate





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Update-CMCertificate [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMCertificate [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMCertificate [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> -X509Certificate <X509Certificate> [-Confirm] [-WhatIf] [<CommonParameters>]
```
