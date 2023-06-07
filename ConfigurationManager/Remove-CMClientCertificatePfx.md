Remove-CMClientCertificatePfx
-----------------------------




### Synopsis
Removes a PFX client certificate.



---


### Description

The Remove-CMClientCertificatePFX removes a client Personal Information Exchange (PFX) certificate from a site server.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCertificateProfilePfx](Get-CMCertificateProfilePfx)



* [Get-CMClientCertificatePfx](Get-CMClientCertificatePfx)



* [Get-CMUser](Get-CMUser)



* [Import-CMClientCertificatePfx](Import-CMClientCertificatePfx)





---


### Examples
#### Example 1: Remove a PFX client certificate by using the pipeline
```PowerShell
PS XYZ:\> Get-CMClientCertificatePfx -UserName (Get-CMUser -Name "Contoso\Administrator01").SMSID -Thumbprint e1c2fff14282b61f79f78fbfca6721f0517ab767 | Remove-CMClientCertificatePfx
```
This command gets the client Pfx certificate object for the user named Administrator01 with the specified thumbprint and uses the pipeline operator to pass the object to Remove-CMClientCertificatePfx , which removes the certificate.
#### Example 2: Remove a PFX client certificate by name
```PowerShell
PS XYZ:\> Remove-CMClientCertificatePfx -Username (Get-CMUser -Name "Contoso\Administrator02").SMSID -Thumbprint e1c2fff14282b61f79f78fbfca6721f0517ab767
```
This command removes the client Pfx certificate for the user named Administrator02 with the specified thumbprint.


---


### Parameters
#### **CertificateProfilePfx**

Specifies a PFX certificate profile object. To obtain a PFX certificate object, use the Get-CMCertificateProfilePfx cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



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



#### **InputObject**

Specifies a client PFX certificate object. To obtain a client PFX certificate object, use the Get-CMClientCertificatePfx cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Thumbprint**

Specifies the thumbprint of a client PFX certificate.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserName**

Specifies the user for whom you want to remove a client PFX certificate. To set a value to the parameter, you can use `(get-cmuser -name domain\username).SMSID`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMClientCertificatePfx [-CertificateProfilePfx <IResultObject>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Thumbprint <String>] -UserName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMClientCertificatePfx [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
