Get-CMBoundaryGroup
-------------------




### Synopsis
Get a boundary group.



---


### Description

Use the Get-CMBoundaryGroup cmdlet to get a boundary group. A boundary group is a collection of boundaries.



You can use boundary groups to manage network locations. Before you can use the boundary group, assign boundaries to boundary groups . Boundary groups enable client computers to find a primary site for client assignment, and a list of available site systems that have content. For more information about boundaries, see Overview of boundaries and boundary groups in Configuration Manager (/mem/configmgr/core/servers/deploy/configure/define-site-boundaries-and-boundary-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMBoundaryGroup](New-CMBoundaryGroup)



* [Remove-CMBoundaryGroup](Remove-CMBoundaryGroup)



* [Set-CMBoundaryGroup](Set-CMBoundaryGroup)



* [Get-CMBoundaryGroupSiteSystem](Get-CMBoundaryGroupSiteSystem)



* [Overview of boundaries and boundary groups in Configuration Manager](Overview of boundaries and boundary groups in Configuration Manager)





---


### Examples
#### Example 1: Get a boundary group that is specified by its name
```PowerShell
Get-CMBoundaryGroup -Name "BGroup01"
```

#### Example 2: Get multiple boundary groups that are specified by ID
```PowerShell
Get-CMBoundaryGroup -Id 5,6
```



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



#### **Id**

Specify an array of group IDs for one or more boundary groups. This value is an integer, for example `5`.






|Type        |Required|Position|PipelineInput|Aliases|
|------------|--------|--------|-------------|-------|
|`[String[]]`|true    |named   |False        |GroupId|



#### **Name**

Specify the name for a boundary group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_BoundaryGroup


* IResultObject#SMS_BoundaryGroup






---


### Notes
For more information on this return object and its properties, see SMS_BoundaryGroup server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_boundarygroup-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMBoundaryGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String[]> [<CommonParameters>]
```
```PowerShell
Get-CMBoundaryGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
