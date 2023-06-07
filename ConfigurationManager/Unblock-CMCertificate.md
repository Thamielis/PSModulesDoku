Unblock-CMCertificate
---------------------




### Synopsis
Unblocks certificates.



---


### Description

The Unblock-CMCertificate cmdlet unblocks one or more public key infrastructure (PKI) certificates that Configuration Manager uses.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Block-CMCertificate](Block-CMCertificate)



* [Import-CMCertificate](Import-CMCertificate)



* [Update-CMCertificate](Update-CMCertificate)





---


### Examples
#### Example 1: Unblock a certificate
```PowerShell
PS XYZ:\>Unblock-CMCertificate -Id "BaseCert.txt"
```
This command unblocks the PKI certificate named BaseCert.


---


### Parameters
#### **Certificate**








|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |named   |True (ByValue)|InputObject|



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



#### **Id**

Specifies an array of IDs of certificates.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |SMSID  |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Unblock-CMCertificate -Certificate <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Unblock-CMCertificate [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
