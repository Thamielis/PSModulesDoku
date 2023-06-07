Get-CMFileReplicationRoute
--------------------------




### Synopsis
Gets a file replication route from Configuration Manager.



---


### Description

The Get-CMFileReplicationRoute cmdlet gets a file replication route from Configuration Manager. Configuration Manager uses file replication routes to transfer file-based data between sites in a hierarchy. Each file replication route identifies a destination site to which file-based data can transfer.



File replication were known as addresses in versions of Configuration Manager before Configuration Manager. The functionality of file replication routes is the same as that of addresses in earlier versions.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMFileReplicationRoute](New-CMFileReplicationRoute)



* [Remove-CMFileReplicationRoute](Remove-CMFileReplicationRoute)



* [Set-CMFileReplicationRoute](Set-CMFileReplicationRoute)





---


### Examples
#### Example 1: Get a file replication route by using site codes
```PowerShell
PS XYZ:\> Get-CMFileReplicationRoute -DestinationSiteCode "IM5" -SourceSiteCode "IM1"
```
This command creates a file replication route from the site that has the site code IM1 to the site that has the site code IM5.


---


### Parameters
#### **DestinationSiteCode**

Specifies a destination site for data transfers by using a site code.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |DesSiteCode|



#### **DestinationSiteName**

Specifies a destination site for data transfers by using a site name.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |DesSiteName|



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



#### **SourceSiteCode**

Specifies a source site for data transfers by using a site code.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |SiteCode|



#### **SourceSiteName**

Specifies a destination site for data transfers by using a site name.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |SiteName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SCI_Address


* IResultObject#SMS_SCI_Address






---


### Notes




---


### Syntax
```PowerShell
Get-CMFileReplicationRoute [-DestinationSiteCode <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SourceSiteCode <String>] [<CommonParameters>]
```
```PowerShell
Get-CMFileReplicationRoute [-DestinationSiteName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SourceSiteName <String>] [<CommonParameters>]
```
