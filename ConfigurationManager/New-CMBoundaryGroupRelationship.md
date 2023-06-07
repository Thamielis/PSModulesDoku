New-CMBoundaryGroupRelationship
-------------------------------




### Synopsis
Create a boundary group relationship.



---


### Description

Use this cmdlet to create a relationship between boundary groups. Boundary groups that you link together are called neighbor boundary groups. A boundary group can have more than one relationship, each with a specific neighbor boundary group.



When a client fails to find an available site system in its current boundary group, the configuration of each relationship determines when it begins to search a neighbor boundary group. This search of other groups is called fallback .



For more information, see Configure boundary groups for Configuration Manager (/mem/configmgr/core/servers/deploy/configure/boundary-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBoundaryGroupRelationship](Get-CMBoundaryGroupRelationship)



* [Remove-CMBoundaryGroupRelationship](Remove-CMBoundaryGroupRelationship)



* [Set-CMBoundaryGroupRelationship](Set-CMBoundaryGroupRelationship)



* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)



* [Configure boundary groups for Configuration Manager](Configure boundary groups for Configuration Manager)





---


### Examples
#### Example 1: Create a relationship for only content
```PowerShell
New-CMBoundaryGroupRelationship -SourceGroupName "Swindon" -DestinationGroupName "London" -FallbackDPMinutes 5 -FallbackSupMinutes -1 -FallbackMPMinutes -1
```



---


### Parameters
#### **DestinationGroup**

Specify a boundary group object for the neighbor. To get this object, use the Get-CMBoundaryGroup (Get-CMBoundaryGroup.md)cmdlet.


The destination boundary group can't be the same as the source boundary group.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **DestinationGroupId**

Specify the ID of the neighbor boundary group. This integer value is the GroupID property.


The destination boundary group can't be the same as the source boundary group.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **DestinationGroupName**

Specify the name of the neighbor boundary group.


The destination boundary group can't be the same as the source boundary group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FallbackDPMinutes**

Specify an integer value for the fallback time in minutes for distribution points (DP) from the source to the destination boundary group. To set the option to Never fallback , specify the value `-1`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **FallbackMPMinutes**

Specify an integer value for the fallback time in minutes for management points (MP) from the source to the destination boundary group. To set the option to Never fallback , specify the value `-1`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **FallbackSmpMinutes**

Specify an integer value for the fallback time in minutes for state migration points (SMP) from the source to the destination boundary group. To set the option to Never fallback , specify the value `-1`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **FallbackSupMinutes**

Specify an integer value for the fallback time in minutes for software update points (SUP) from the source to the destination boundary group. To set the option to Never fallback , specify the value `-1`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SourceGroup**

Specify a boundary group object from which to create the relationship. To get this object, use the Get-CMBoundaryGroup (Get-CMBoundaryGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SourceGroupId**

Specify the ID of the boundary group from which to create the relationship. This integer value is the GroupID property.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **SourceGroupName**

Specify the name of the boundary group from which to create the relationship.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_BoundaryGroupRelationships






---


### Notes




---


### Syntax
```PowerShell
New-CMBoundaryGroupRelationship -DestinationGroup <IResultObject> [-DisableWildcardHandling] [-FallbackDPMinutes <Int32>] [-FallbackMPMinutes <Int32>] [-FallbackSmpMinutes <Int32>] [-FallbackSupMinutes <Int32>] [-ForceWildcardHandling] -SourceGroup <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMBoundaryGroupRelationship -DestinationGroupId <Int32> [-DisableWildcardHandling] [-FallbackDPMinutes <Int32>] [-FallbackMPMinutes <Int32>] [-FallbackSmpMinutes <Int32>] [-FallbackSupMinutes <Int32>] [-ForceWildcardHandling] -SourceGroupId <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMBoundaryGroupRelationship -DestinationGroupName <String> [-DisableWildcardHandling] [-FallbackDPMinutes <Int32>] [-FallbackMPMinutes <Int32>] [-FallbackSmpMinutes <Int32>] [-FallbackSupMinutes <Int32>] [-ForceWildcardHandling] -SourceGroupName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
