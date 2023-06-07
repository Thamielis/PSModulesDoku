Get-CMBoundaryGroupSiteSystem
-----------------------------




### Synopsis
Get site systems in the specified boundary group



---


### Description

Use this cmdlet to get site systems in the specified boundary group. For more information, see About boundary groups in Configuration Manager (/mem/configmgr/core/servers/deploy/configure/boundary-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)



* [Get-CMBoundaryGroupRelationship](Get-CMBoundaryGroupRelationship)





---


### Examples
#### Example 1: Display FQDNs of site systems in a boundary group
```PowerShell
$bgName = "Contoso HQ BG"
$boundaryGroup = Get-CMBoundaryGroup -Name $bgName

$bgSiteSystems = Get-CMBoundaryGroupSiteSystem -InputObject $boundaryGroup

foreach ($system in $bgSiteSystems) {
  Write-Host $system.ServerNalPath.TrimEnd('\').Split('\')[-1]
}
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



#### **GroupName**

Specify a boundary group name to get the associated site systems.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Id**

Specify an array of boundary group IDs to get the associated site systems. This value is an integer, for example `5`.






|Type        |Required|Position|PipelineInput|Aliases|
|------------|--------|--------|-------------|-------|
|`[String[]]`|true    |named   |False        |GroupId|



#### **InputObject**

Specify a boundary group object to get the associated site systems. To get this object, use the Get-CMBoundaryGroup (Get-CMBoundaryGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases      |
|-----------------|--------|--------|--------------|-------------|
|`[IResultObject]`|false   |named   |True (ByValue)|BoundaryGroup|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_BoundaryGroupSiteSystems


* IResultObject#SMS_BoundaryGroupSiteSystems






---


### Notes
For more information on this return object and its properties, see SMS_BoundaryGroupSiteSystems server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_boundarygroupsitesystems-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMBoundaryGroupSiteSystem [-DisableWildcardHandling] [-ForceWildcardHandling] [-GroupName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMBoundaryGroupSiteSystem [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String[]> [<CommonParameters>]
```
```PowerShell
Get-CMBoundaryGroupSiteSystem [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IResultObject>] [<CommonParameters>]
```
