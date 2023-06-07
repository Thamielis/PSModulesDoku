Remove-CMCertificateRegistrationPoint
-------------------------------------




### Synopsis
Removes a certificate registration point role from a site system server.



---


### Description

The Remove-CMCertificateRegistrationPoint cmdlet removes a certificate registration point role from a site system server.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMCertificateRegistrationPoint](Add-CMCertificateRegistrationPoint)



* [Get-CMCertificateRegistrationPoint](Get-CMCertificateRegistrationPoint)



* [Set-CMCertificateRegistrationPoint](Set-CMCertificateRegistrationPoint)





---


### Examples
#### Example 1: Remove a certificate registration point role by using the pipeline
```PowerShell
PS XYZ:\> Get-CMCertificateRegistrationPoint -SiteSystemServerName "SiteSystemserver01.Contoso.com" | Remove-CMCertificateRegistrationPoint -Force
```
This command gets the certificate registration point object for the site system server named SiteSystemserver01.Contoso.com and uses the pipeline operator to pass the object to Remove-CMCertificateRegistrationPoint , which removes the certificate registration point. The command does not prompt the user for confirmation.
#### Example 2: Remove a certificate registration point role by name
```PowerShell
PS XYZ:\> Remove-CMCertificateRegistrationPoint -SiteSystemServerName "SiteSystemserver02.Contoso.com"
```
This command removes the certificate registration point from the site system server named SiteSystemserver02.Contoso.com.


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



#### **InputObject**

Specifies a certificate registration point role object. To obtain a certificate registration point role object, use the Get-CMCertificateRegistrationPoint cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                     |
|-----------------|--------|--------|--------------|----------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|CertificateRegistrationPoint|



#### **SiteCode**

Specifies the site code of the Configuration Manager site server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of the Configuration Manager site system server.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



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
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMCertificateRegistrationPoint [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCertificateRegistrationPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
