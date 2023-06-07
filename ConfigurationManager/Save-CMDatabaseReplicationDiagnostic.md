Save-CMDatabaseReplicationDiagnostic
------------------------------------




### Synopsis
Saves database replication diagnostic information for Configuration Manager in a file.



---


### Description

The Save-CMDatabaseReplicationDiagnostic cmdlet saves diagnostic information for database replication issues for Configuration Manager in a specified file. This cmdlet runs diagnostics for a link between a parent and a child site databases. You can specify sites by either name or site code, but you cannot specify one site by name and the other by site code.



Configuration Manager database replication transfers data and merges changes made in a site database with the information stored in other sites in the Configuration Manager site hierarchy so that all sites share the same information. Configuration Manager configures database replication automatically between a parent and child site. Diagnostics identify problems in database replication.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDatabaseReplicationLinkProperty](Get-CMDatabaseReplicationLinkProperty)



* [Get-CMDataBaseReplicationStatus](Get-CMDataBaseReplicationStatus)





---


### Examples
#### Example 1: Save database replication diagnostic
```PowerShell
PS XYZ:\> Save-CMDatabaseReplicationDiagnostic -ChildSiteCode "CC2" -FileName "D:\Diagnostics\CCB_CC2_Diagnostics.csv" -ParentSiteCode "CCB"
```
This command saves database replication diagnostics in a file named CCB_CC2_Diagnostics.csv. The command specifies a parent and child site by using site codes.


---


### Parameters
#### **ChildSiteCode**

Specifies a site code for a Configuration Manager site. This is the child site.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Site2  |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileName**

Specifies a file name. This cmdlet saves database diagnostic information for database replication to this file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteCode**








|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|false   |named   |False        |Site1<br/>ParentSiteCode|



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
* [String](https://learn.microsoft.com/en-us/dotnet/api/System.String)






---


### Notes




---


### Syntax
```PowerShell
Save-CMDatabaseReplicationDiagnostic -ChildSiteCode <String> [-DisableWildcardHandling] [-FileName <String>] [-ForceWildcardHandling] [-PassThru] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
