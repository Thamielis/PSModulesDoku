Set-CMBoundaryGroup
-------------------




### Synopsis
Modify the properties of a boundary group.



---


### Description

The Set-CMBoundaryGroup cmdlet modifies the properties of a boundary group. A boundary group is a collection of boundaries. For more information, see Define site boundaries and boundary groups (/mem/configmgr/core/servers/deploy/configure/define-site-boundaries-and-boundary-groups) and the [New-CMBoundary](New-CMBoundary.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)



* [New-CMBoundaryGroup](New-CMBoundaryGroup)



* [Remove-CMBoundaryGroup](Remove-CMBoundaryGroup)



* [Set-CMSecurityScope](Set-CMSecurityScope)



* [New-CMBoundary](New-CMBoundary)



* [Define site boundaries and boundary groups](Define site boundaries and boundary groups)





---


### Examples
#### Example 1: Rename a boundary group
```PowerShell
Get-CMBoundaryGroup -Name "BGroup01" | Set-CMBoundaryGroup -NewName "BGroup00"
```

#### Example 2: Add a security scope to a boundary group
```PowerShell
Set-CMBoundaryGroup -SecurityScopeAction AddMembership -SecurityScopeName "OSDeploymentScope" -Name "BGroup02"
```

#### Example 3: Add a site system server
```PowerShell
$server = Get-CMSiteSystemServer -Name "granitefalls.cloudapp.net"
Set-CMBoundaryGroup -Name "Remote BG" -AddSiteSystemServer $server
```



---


### Parameters
#### **AddSiteSystemServer**

Specify a site system server object to add to this boundary group. Clients on the boundary group use these servers for policy and content. You can add management points, distribution points, state migration points, software update points, and cloud management gateways. To get a site system server object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases             |
|-------------------|--------|--------|-------------|--------------------|
|`[IResultObject[]]`|false   |named   |False        |AddSiteSystemServers|



#### **AddSiteSystemServerName**

Specify the fully qualified domain name of a site system server to add to this boundary group. Clients on the boundary group use these servers for policy and content. You can add management points, distribution points, state migration points, software update points, and cloud management gateways.


> [!Important] > This parameter requires the fully qualified domain name of the site server.






|Type        |Required|Position|PipelineInput|Aliases                 |
|------------|--------|--------|-------------|------------------------|
|`[String[]]`|false   |named   |False        |AddSiteSystemServerNames|



#### **AllowPeerDownload**

Configure the boundary group option to allow peer downloads in this boundary group. For more information, see Boundary group options for peer downloads (/mem/configmgr/core/servers/deploy/configure/boundary-groups#bkmk_bgoptions).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClearSiteSystemServer**

Add this parameter to remove all referenced site system servers from the boundary group.






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[Switch]`|false   |named   |False        |ClearSiteSystemServers|



#### **DefaultSiteCode**

Specify the site code to set as the assigned site, and enable the boundary group for site assignment.


To disable site assignment for the boundary group, set this value to `$null`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Description**

Specify an optional description for this boundary group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **Id**

Specify the ID of a boundary group to configure. This ID is the GroupID property on the SMS_BoundaryGroup (/mem/configmgr/develop/reference/core/servers/configure/sms_boundarygroup-server-wmi-class)object. For example, `33`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |GroupId|



#### **InputObject**

Specify an object for a boundary group to configure. To get a boundary group object, use the Get-CMBoundaryGroup (Get-CMBoundaryGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name for a boundary group to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Use this parameter to rename a boundary group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PreferCloudDPOverDP**

Configure the boundary group option to prefer cloud-based sources over on-premises sources. For more information, see Boundary group options for peer downloads (/mem/configmgr/core/servers/deploy/configure/boundary-groups#bkmk_bgoptions).






|Type       |Required|Position|PipelineInput|Aliases                                          |
|-----------|--------|--------|-------------|-------------------------------------------------|
|`[Boolean]`|false   |named   |False        |PreferCloudDistributionPointOverDistributionPoint|



#### **PreferDPOverPeer**

Configure the boundary group option to prefer distribution points over peers within the same subnet. To enable this setting, also enable -AllowPeerDownload . For more information, see Boundary group options for peer downloads (/mem/configmgr/core/servers/deploy/configure/boundary-groups#bkmk_bgoptions).






|Type       |Required|Position|PipelineInput|Aliases                                |
|-----------|--------|--------|-------------|---------------------------------------|
|`[Boolean]`|false   |named   |False        |PreferDistributionPointOverPeerInSubnet|



#### **RemoveSiteSystemServer**

Specifies a site system server object to remove from the boundary group. To get this object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.


To remove all site system servers, use the -ClearSiteSystemServer parameter.






|Type               |Required|Position|PipelineInput|Aliases                |
|-------------------|--------|--------|-------------|-----------------------|
|`[IResultObject[]]`|false   |named   |False        |RemoveSiteSystemServers|



#### **RemoveSiteSystemServerName**

Specifies the name of one or more site system servers to remove from the boundary group. To remove all site system servers, use the -ClearSiteSystemServer parameter.






|Type        |Required|Position|PipelineInput|Aliases                    |
|------------|--------|--------|-------------|---------------------------|
|`[String[]]`|false   |named   |False        |RemoveSiteSystemServerNames|



#### **SubnetPeerDownloadOnly**

Configure the boundary group option to only use peers within the same subnet during peer downloads. To enable this setting, also enable -AllowPeerDownload . For more information, see Boundary group options for peer downloads (/mem/configmgr/core/servers/deploy/configure/boundary-groups#bkmk_bgoptions).






|Type       |Required|Position|PipelineInput|Aliases                 |
|-----------|--------|--------|-------------|------------------------|
|`[Boolean]`|false   |named   |False        |PeerWithinSameSubnetOnly|



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_BoundaryGroup






---


### Notes




---


### Syntax
```PowerShell
Set-CMBoundaryGroup [-AddSiteSystemServer <IResultObject[]>] [-AddSiteSystemServerName <String[]>] [-AllowPeerDownload <Boolean>] [-ClearSiteSystemServer] [-DefaultSiteCode <String>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-PassThru] [-PreferCloudDPOverDP <Boolean>] [-PreferDPOverPeer <Boolean>] [-RemoveSiteSystemServer <IResultObject[]>] [-RemoveSiteSystemServerName <String[]>] [-SubnetPeerDownloadOnly <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBoundaryGroup [-AddSiteSystemServer <IResultObject[]>] [-AddSiteSystemServerName <String[]>] [-AllowPeerDownload <Boolean>] [-ClearSiteSystemServer] [-DefaultSiteCode <String>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-PreferCloudDPOverDP <Boolean>] [-PreferDPOverPeer <Boolean>] [-RemoveSiteSystemServer <IResultObject[]>] [-RemoveSiteSystemServerName <String[]>] [-SubnetPeerDownloadOnly <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBoundaryGroup [-AddSiteSystemServer <IResultObject[]>] [-AddSiteSystemServerName <String[]>] [-AllowPeerDownload <Boolean>] [-ClearSiteSystemServer] [-DefaultSiteCode <String>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-PreferCloudDPOverDP <Boolean>] [-PreferDPOverPeer <Boolean>] [-RemoveSiteSystemServer <IResultObject[]>] [-RemoveSiteSystemServerName <String[]>] [-SubnetPeerDownloadOnly <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
