New-CMADGroupDiscoveryScope
---------------------------




### Synopsis
Creates an Active Directory group discovery scope.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



---


### Parameters
#### **DisableWildcardHandling**

DisableWildcardHandling treats wildcard characters as literal character values. Can't be combined with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DiscoveryAccountUserName**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |UserName|



#### **DomainControllerServerName**








|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |DCName |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GroupDN**








|Type        |Required|Position|PipelineInput|Aliases |
|------------|--------|--------|-------------|--------|
|`[String[]]`|true    |named   |False        |GroupDNs|



#### **LdapLocation**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **RecursiveSearch**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SiteCode**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* ADGroupDiscoveryScope


* ADGroupGroupDiscoveryScope


* ADGroupLocationDiscoveryScope






---


### Notes




---


### Syntax
```PowerShell
New-CMADGroupDiscoveryScope [-Name] <String> [-DisableWildcardHandling] [-DiscoveryAccountUserName <String>] [-DomainControllerServerName <String>] [-ForceWildcardHandling] -GroupDN <String[]> [-SiteCode <String>] [<CommonParameters>]
```
```PowerShell
New-CMADGroupDiscoveryScope [-Name] <String> [-DisableWildcardHandling] [-DiscoveryAccountUserName <String>] [-ForceWildcardHandling] -LdapLocation <String> [-RecursiveSearch <Boolean>] [-SiteCode <String>] [<CommonParameters>]
```
