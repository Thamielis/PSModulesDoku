Get-CMActiveDirectorySite
-------------------------




### Synopsis
Gets Configuration Manager sites that publish data to AD DS.



---


### Description

The Get-CMActiveDirectorySite cmdlet gets one or more Configuration Manager sites that are configured to publish site information to Active Directory� Domain Services (AD DS). You can get Configuration Manager sites that publish site data to AD DS by using an identifier or a fully qualified domain name (FQDN).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMActiveDirectoryForest](Get-CMActiveDirectoryForest)





---


### Examples
#### Example 1: Get an Active Directory site
```PowerShell
PS XYZ:\> Get-CMActiveDirectorySite
```
This command gets the Active Directory sites that are configured to publish site information.


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



#### **ForestFqdn**

Specifies an array of fully qualified domain names that identify Active Directory forests. The FQDN provides a path to an Active Directory forest.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **ForestId**

Specifies an array of IDs that identify Active Directory forests.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|true    |named   |False        |



#### **Id**

Specifies an array of identifiers of Active Directory forest objects that contain Active Directory sites.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |SiteId |



#### **Name**

Specifies an array of FQDNs of Active Directory forest objects that contain Active Directory sites.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |ADSiteName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_ADSite


* IResultObject#SMS_ADSite






---


### Notes




---


### Syntax
```PowerShell
Get-CMActiveDirectorySite [-DisableWildcardHandling] [-ForceWildcardHandling] -ForestFqdn <String[]> [<CommonParameters>]
```
```PowerShell
Get-CMActiveDirectorySite [-DisableWildcardHandling] [-ForceWildcardHandling] -ForestId <String[]> [<CommonParameters>]
```
```PowerShell
Get-CMActiveDirectorySite [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMActiveDirectorySite [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
