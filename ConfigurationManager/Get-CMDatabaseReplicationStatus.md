Get-CMDatabaseReplicationStatus
-------------------------------




### Synopsis
Gets the status for database replication.



---


### Description

The Get-CMDatabaseReplicationStatus cmdlet gets the status of the database replication link for a Configuration Manager parent/child site pair. The cmdlet identifies the sites by site code.



You can specify just the site code or just the name for a parent or child and get all the database replication links for the specified site.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Get status using site codes
```PowerShell
PS XYZ:\> Get-CMDataBaseReplicationStatus -ChildSiteCode "CCC" -ParentSiteCode "CCA"
```
This command gets the status of a database replication link for the child with a site code CCC and the parent with a site code CCA.


---


### Parameters
#### **ChildSiteCode**

Specifies a site code for a child site.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Site2  |



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

Specifies a site code for a parent site.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Site1  |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_ReplicationLinkSummary


* IResultObject#SMS_ReplicationLinkSummary






---


### Notes




---


### Syntax
```PowerShell
Get-CMDatabaseReplicationStatus [-ChildSiteCode <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ParentSiteCode <String>] [<CommonParameters>]
```
