Remove-CMFileReplicationRoute
-----------------------------




### Synopsis
Removes a file replication route from Configuration Manager.



---


### Description

The Remove-CMFileReplicationRoute cmdlet removes a file replication route from Configuration Manager. Configuration Manager uses file replication routes to transfer file-based data between sites in a hierarchy. Each file replication route identifies a destination site to which file-based data can transfer.



File replication routes were known as addresses in versions of Configuration Manager before Configuration Manager. The functionality of file replication routes is the same as that of addresses in earlier versions.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMFileReplicationRoute](Get-CMFileReplicationRoute)



* [New-CMFileReplicationRoute](New-CMFileReplicationRoute)



* [Set-CMFileReplicationRoute](Set-CMFileReplicationRoute)





---


### Examples
#### Example 1: Remove a file replication route
```PowerShell
PS XYZ:\> Remove-CMFileReplicationRoute -DestinationSiteCode "IM5" -SourceSiteCode "IM1"
```
This command removes a file replication route from the site that has the site code IM1 to the site that has the site code IM5.


---


### Parameters
#### **DestinationSiteCode**

Specifies the destination site code for the file replication route that you remove.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |DesSiteCode|



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



#### **SourceSiteCode**

Specifies the source site code for the file replication route that you remove.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteCode|



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
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMFileReplicationRoute -DestinationSiteCode <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SourceSiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
