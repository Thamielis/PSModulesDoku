Get-CMBoundaryGroupRelationship
-------------------------------




### Synopsis
Get a boundary group relationship.



---


### Description

Use this cmdlet to get the relationship between boundary groups. For more information, see Configure boundary groups for Configuration Manager (/mem/configmgr/core/servers/deploy/configure/boundary-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMBoundaryGroupRelationship](New-CMBoundaryGroupRelationship)



* [Remove-CMBoundaryGroupRelationship](Remove-CMBoundaryGroupRelationship)



* [Set-CMBoundaryGroupRelationship](Set-CMBoundaryGroupRelationship)



* [Get-CMBoundaryGroupSiteSystem](Get-CMBoundaryGroupSiteSystem)



* [Configure boundary groups for Configuration Manager](Configure boundary groups for Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Get-CMBoundaryGroupRelationship -DestinationGroupName "Swindon" -SourceGroupName "London"
```



---


### Parameters
#### **DestinationGroupId**

Specify the ID of the neighbor boundary group. This integer value is the GroupID property.


The destination boundary group can't be the same as the source boundary group.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DestinationGroupName**

Specify the name of the neighbor boundary group.


The destination boundary group can't be the same as the source boundary group.






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



#### **SourceGroupId**

Specify the ID of the boundary group that has the relationship. This integer value is the GroupID property.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SourceGroupName**

Specify the name of the boundary group that has the relationship.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_BoundaryGroupRelationships


* IResultObject#SMS_BoundaryGroupRelationships






---


### Notes
For more information on this return object and its properties, see SMS_BoundaryGroupRelationships server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms-boundarygrouprelationships-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMBoundaryGroupRelationship [-DestinationGroupId <Int32>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SourceGroupId <Int32>] [<CommonParameters>]
```
```PowerShell
Get-CMBoundaryGroupRelationship [-DestinationGroupName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SourceGroupName <String>] [<CommonParameters>]
```
