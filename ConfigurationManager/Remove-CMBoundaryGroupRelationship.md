Remove-CMBoundaryGroupRelationship
----------------------------------




### Synopsis
Remove a boundary group relationship.



---


### Description

Use this cmdlet to remove the relationship between boundary groups. For more information, see Configure boundary groups for Configuration Manager (/mem/configmgr/core/servers/deploy/configure/boundary-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBoundaryGroupRelationship](Get-CMBoundaryGroupRelationship)



* [New-CMBoundaryGroupRelationship](New-CMBoundaryGroupRelationship)



* [Set-CMBoundaryGroupRelationship](Set-CMBoundaryGroupRelationship)



* [Configure boundary groups for Configuration Manager](Configure boundary groups for Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Remove-CMBoundaryGroupRelationship -DestinationGroupName "Swindon" -SourceGroupName "London" -Force
```



---


### Parameters
#### **DestinationGroupId**

Specify the ID of the neighbor boundary group to remove. This integer value is the GroupID property.


The destination boundary group can't be the same as the source boundary group.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DestinationGroupName**

Specify the name of the neighbor boundary group to remove.


The destination boundary group can't be the same as the source boundary group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a boundary group relationship object to remove. To get this object, use the Get-CMBoundaryGroupRelationship (Get-CMBoundaryGroupRelationship.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SourceGroupId**

Specify the ID of the boundary group from which to remove the relationship. This integer value is the GroupID property.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **SourceGroupName**

Specify the name of the boundary group from which to remove the relationship.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMBoundaryGroupRelationship [-DestinationGroupId <Int32>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SourceGroupId <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryGroupRelationship [-DestinationGroupName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-SourceGroupName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryGroupRelationship [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
