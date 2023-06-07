Get-CMActiveDirectoryForest
---------------------------




### Synopsis
Gets one or more Active Directory forest objects.



---


### Description

The Get-CMActiveDirectoryForest cmdlet gets one or more Active Directory forest objects in Configuration Manager. You can get an Active Directory forest object by ID or fully qualified domain name (FQDN).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMActiveDirectoryForest](New-CMActiveDirectoryForest)



* [Set-CMActiveDirectoryForest](Set-CMActiveDirectoryForest)



* [Remove-CMActiveDirectoryForest](Remove-CMActiveDirectoryForest)





---


### Examples
#### Example 1: Get all Active Directory forest objects
```PowerShell
PS XYZ:\> Get-CMActiveDirectoryForest
```
This command gets all Active Directory forest objects.
#### Example 2: Get an Active Directory Forest object by ID
```PowerShell
PS XYZ:\> Get-CMActiveDirectoryForest -Id "16777217"
```
This command gets an Active Directory forest object that has the ID 16777217.
#### Example 3: Get Active Directory Forest by domain name
```PowerShell
PS XYZ:\> Get-CMActiveDirectoryForest -ForestFqdn "tsqa.contoso.com"
```
This command gets an Active Directory forest object that has the FQDN tsqa.contoso.com.


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

Specifies the FQDN of a Configuration Manager object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Id**

Specifies an array of IDs of Configuration Manager objects. You can find the identifier value in the ForestID property of an Active Directory forest.






|Type        |Required|Position|PipelineInput|Aliases |
|------------|--------|--------|-------------|--------|
|`[String[]]`|true    |named   |False        |ForestId|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_ADForest


* IResultObject#SMS_ADForest






---


### Notes




---


### Syntax
```PowerShell
Get-CMActiveDirectoryForest [-DisableWildcardHandling] [-ForceWildcardHandling] [-ForestFqdn <String>] [<CommonParameters>]
```
```PowerShell
Get-CMActiveDirectoryForest [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String[]> [<CommonParameters>]
```
