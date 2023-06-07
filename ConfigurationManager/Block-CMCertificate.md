Block-CMCertificate
-------------------




### Synopsis
Blocks a certificate.



---


### Description

The Block-CMCertificate cmdlet blocks a certificate. Configuration Manager uses certificates to manage boot media, Pre-Boot eXecution Environment (PXE) deployments, and Independent Software Vendors (ISV) proxies.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Import-CMCertificate](Import-CMCertificate)



* [Unblock-CMCertificate](Unblock-CMCertificate)



* [Update-CMCertificate](Update-CMCertificate)





---


### Examples
#### Example 1: Block a certificate
```PowerShell
PS XYZ:\>Block-CMCertificate -Id "11729"
```
This command blocks the certificate that has the specified ID.


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



#### **Id**

Specifies an array of certificate IDs.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |0       |False        |SmsId  |



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |0       |True (ByValue)|Certificate|



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
Block-CMCertificate [-Id] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Block-CMCertificate [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
