New-CMFileReplicationRoute
--------------------------




### Synopsis
Creates a file replication route for Configuration Manager.



---


### Description

The New-CMFileReplicationRoute cmdlet creates a file replication route for Configuration Manager. Configuration Manager uses file replication routes to transfer file-based data between sites in a hierarchy. Each file replication route identifies a destination site to which file-based data can transfer.



File replication routes were known as addresses in versions of Configuration Manager before Configuration Manager. The functionality of file replication routes is the same as that of addresses in earlier versions.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMFileReplicationRoute](Get-CMFileReplicationRoute)



* [Remove-CMFileReplicationRoute](Remove-CMFileReplicationRoute)



* [Set-CMFileReplicationRoute](Set-CMFileReplicationRoute)





---


### Examples
#### Example 1: Create a file replication route
```PowerShell
PS XYZ:\> New-CMFileReplicationRoute -DestinationSiteCode "IM5" -SourceSiteCode "IM1" -DestinationSiteServerName "ImgDataServer01" -FileReplicationAccountName "AdminRepl01"
```
This command creates a file replication route from the site that has the site code IM1 to the site that has the site code IM5 on the server named ImgDataServer01. Configuration Manager uses the account named AdminRepl01 to manage data transfer over this route.


---


### Parameters
#### **DestinationSiteCode**

Specifies a destination site for data transfers by using a site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DestinationSiteServerName**

Specifies a destination site server for data transfers by using a site server name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileReplicationAccountName**

Specifies the account that Configuration Manager uses to install a site on the specified server and maintain communications between the site and other sites. This account must have local administrative credentials.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SourceSiteCode**

Specifies a source site for data transfers by using a site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
* IResultObject#SMS_SCI_Address






---


### Notes




---


### Syntax
```PowerShell
New-CMFileReplicationRoute -DestinationSiteCode <String> [-DestinationSiteServerName <String>] [-DisableWildcardHandling] [-FileReplicationAccountName <String>] [-ForceWildcardHandling] -SourceSiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
