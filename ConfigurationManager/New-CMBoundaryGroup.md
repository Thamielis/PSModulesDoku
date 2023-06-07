New-CMBoundaryGroup
-------------------




### Synopsis
Creates a new boundary group.



---


### Description

The New-CMBoundaryGroup cmdlet creates a new boundary group. A boundary group is a collection of boundaries.



You can use boundary groups to manage network locations. You must assign boundaries to boundary groups before you can use the boundary group. Boundary groups enable client computers to find a primary site for client assignment, which is referred to as automatic site assignment, and a list of available site systems that have content. For more information about boundaries, see Planning for Boundaries and Boundary Groups in Configuration Manager (/mem/configmgr/core/servers/deploy/configure/define-site-boundaries-and-boundary-groups) and the [New-CMBoundary](New-CMBoundary.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Define site boundaries and boundary groups for Configuration Manager](Define site boundaries and boundary groups for Configuration Manager)



* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)



* [Remove-CMBoundaryGroup](Remove-CMBoundaryGroup)



* [Set-CMBoundaryGroup](Set-CMBoundaryGroup)



* [New-CMBoundary](New-CMBoundary)





---


### Examples
#### Example 1: Create a new boundary group
```PowerShell
New-CMBoundaryGroup -Name "BGroup05"
```



---


### Parameters
#### **AddSiteSystemServer**

Specifies the site system server and link speed as the key/value pair in a hash table. Valid values are:


* FastLink


* Slowlink




For example: @{"Server01.contoso.com" = "FastLink"} Important : Starting in version 1610, FastLink is the only supported value for the hash table.







|Type               |Required|Position|PipelineInput|Aliases             |
|-------------------|--------|--------|-------------|--------------------|
|`[IResultObject[]]`|false   |named   |False        |AddSiteSystemServers|



#### **AddSiteSystemServerName**








|Type        |Required|Position|PipelineInput|Aliases                 |
|------------|--------|--------|-------------|------------------------|
|`[String[]]`|false   |named   |False        |AddSiteSystemServerNames|



#### **DefaultSiteCode**

Specifies the default site code for the boundary group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Description**

Specifies a description for the new boundary.






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



#### **Name**

Specifies a name for the new boundary.






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
* IResultObject#SMS_BoundaryGroup






---


### Notes




---


### Syntax
```PowerShell
New-CMBoundaryGroup [-AddSiteSystemServer <IResultObject[]>] [-AddSiteSystemServerName <String[]>] [-DefaultSiteCode <String>] [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
