New-CMActiveDirectoryForest
---------------------------




### Synopsis
Creates one or more Active Directory forest objects in Configuration Manager.



---


### Description

The New-CMActiveDirectoryForest cmdlet creates an Active Directory forest object that has a fully qualified domain name (FQDN), description, and publishing path that you supply.



If you configured an Active Directory Forest Discovery method, you can enable discovery for an Active Directory forest. After you enable discovery, Configuration Manager discovers Active Directory sites and subnets.



Active Directory Forest Discovery requires a global account to discover or publish to untrusted forests.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMActiveDirectoryForest](Set-CMActiveDirectoryForest)



* [Get-CMActiveDirectoryForest](Get-CMActiveDirectoryForest)



* [Remove-CMActiveDirectoryForest](Remove-CMActiveDirectoryForest)



* [Get-CMActiveDirectorySite](Get-CMActiveDirectorySite)





---


### Examples
#### Example 1: Create an Active Directory forest object that has discovery enabled
```PowerShell
PS XYZ:\> New-CMActiveDirectoryForest -ForestFqdn "tsqa.contoso.com" -EnableDiscovery $True
```
This command creates an Active Directory forest object that has the FQDN tsqa.contoso.com and that has discovery enabled. You must configure an Active Directory Forest Discovery method before discovery can work.


---


### Parameters
#### **Description**

Specifies a description for an Active Directory forest object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableDiscovery**

Specifies whether to discover Active Directory sites and subnets. If you enable discovery, you must configure an Active Directory Forest Discovery method. The default value is $False.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForestFqdn**

Specifies an FQDN of a Configuration Manager object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Password**

{{ Fill Password Description }}






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **PublishingPath**

Specifies one or more Configuration Manager sites that publish site information to an Active Directory forest. You can use a comma-separated list in quotation marks to specify more than one site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
None





---


### Outputs
* IResultObject#SMS_ADForest






---


### Notes




---


### Syntax
```PowerShell
New-CMActiveDirectoryForest [-Description <String>] [-DisableWildcardHandling] [-EnableDiscovery <Boolean>] [-ForceWildcardHandling] -ForestFqdn <String> [-Password <SecureString>] [-PublishingPath <String>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
