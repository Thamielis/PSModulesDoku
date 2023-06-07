Get-CMDatabaseReplicationLinkProperty
-------------------------------------




### Synopsis
Gets a replication link between a Configuration Manager parent site and child site.



---


### Description

The Get-CMDatabaseReplicationLinkProperty cmdlet gets a specified replication link between a Configuration Manager parent site and child site.



Database replication for Configuration Manager sites transfers data and merges changes made in a site database with information stored at other sites in the Configuration Manager hierarchy. This enables all sites to share the same information.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMDatabaseReplicationLinkProperty](Set-CMDatabaseReplicationLinkProperty)





---


### Examples
#### Example 1: Get a replication link
```PowerShell
PS XYZ:\> Get-CMDatabaseReplicationLinkProperty -ChildSiteCode "CM8" -ParentSiteCode "CM1"
```
This command gets a replication link between specified parent and child sites. You must specify both sites.


---


### Parameters
#### **ChildSiteCode**

Specifies a site code for a Configuration Manager site. This parameter refers to the child site.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Site2  |



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



#### **ParentSiteCode**

Specifies a site code for a Configuration Manager site. This parameter refers to the parent site.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Site1  |





---


### Inputs
None





---


### Outputs
* Dictionary<string, object>


* IResultObject#SMS_Alert






---


### Notes




---


### Syntax
```PowerShell
Get-CMDatabaseReplicationLinkProperty -ChildSiteCode <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -ParentSiteCode <String> [<CommonParameters>]
```
