Get-CMClientCertificatePfx
--------------------------




### Synopsis
Get a client PFX certificate.



---


### Description

Use this cmdlet to get a client Personal Information Exchange (PFX) certificate. For more information, see Introduction to certificate profiles in Configuration Manager (/mem/configmgr/protect/deploy-use/introduction-to-certificate-profiles).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCertificateProfilePfx](Get-CMCertificateProfilePfx)



* [Get-CMUser](Get-CMUser)



* [Import-CMClientCertificatePfx](Import-CMClientCertificatePfx)



* [Remove-CMClientCertificatePfx](Remove-CMClientCertificatePfx)





---


### Examples
#### Example 1: Get a client PFX certificate
```PowerShell
Get-CMClientCertificatePfx -UserName (Get-CMUser -Name "contoso\jqpublic").SMSID -Thumbprint e1c2fff14282b61f79f78fbfca6721f0517ab767
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a PFX certificate profile object. To get this object, use the Get-CMCertificateProfilePfx (Get-CMCertificateProfilePfx.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases              |
|-----------------|--------|--------|--------------|---------------------|
|`[IResultObject]`|false   |named   |True (ByValue)|CertificateProfilePfx|



#### **Thumbprint**

Specify the thumbprint of the client PFX certificate. If you don't specify this parameter, it returns all certificates for the user.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserName**

Specify the name of the user whose client PFX certificate you want to get. To get a value for this parameter, you can use the following command: `(Get-CMUser -Name "contoso\jqpublic").SMSID`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_ClientPfxCertificate






---


### Notes
For more information on this return object and its properties, see SMS_ClientPfxCertificate server WMI class (/mem/configmgr/develop/reference/core/clients/deploy/sms_clientpfxcertificate-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMClientCertificatePfx [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Thumbprint <String>] [-UserName <String>] [<CommonParameters>]
```
