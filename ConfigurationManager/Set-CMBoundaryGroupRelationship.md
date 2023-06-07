Set-CMBoundaryGroupRelationship
-------------------------------




### Synopsis
Configure a boundary group relationship.



---


### Description

Use this cmdlet to configure the relationship between boundary groups. For more information, see Configure boundary groups for Configuration Manager (/mem/configmgr/core/servers/deploy/configure/boundary-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBoundaryGroupRelationship](Get-CMBoundaryGroupRelationship)



* [New-CMBoundaryGroupRelationship](New-CMBoundaryGroupRelationship)



* [Remove-CMBoundaryGroupRelationship](Remove-CMBoundaryGroupRelationship)



* [Configure boundary groups for Configuration Manager](Configure boundary groups for Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Get-CMBoundaryGroupRelationship -DestinationGroupName "Swindon" -SourceGroupName "London" | Set-CMBoundaryGroupRelationship -FallbackSupMinutes 120 -FallbackMPMinutes 0
```



---


### Parameters
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



#### **InputObject**

Specify a boundary group relationship object to configure. To get this object, use the Get-CMBoundaryGroupRelationship (Get-CMBoundaryGroupRelationship.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SourceGroupId**

Specify the ID of the boundary group from which to configure the relationship. This integer value is the GroupID property.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **SourceGroupName**

Specify the name of the boundary group from which to configure the relationship.






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
Set-CMBoundaryGroupRelationship -DestinationGroupId <Int32> [-DisableWildcardHandling] [-FallbackDPMinutes <Int32>] [-FallbackMPMinutes <Int32>] [-FallbackSmpMinutes <Int32>] [-FallbackSupMinutes <Int32>] [-ForceWildcardHandling] [-PassThru] -SourceGroupId <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBoundaryGroupRelationship -DestinationGroupName <String> [-DisableWildcardHandling] [-FallbackDPMinutes <Int32>] [-FallbackMPMinutes <Int32>] [-FallbackSmpMinutes <Int32>] [-FallbackSupMinutes <Int32>] [-ForceWildcardHandling] [-PassThru] -SourceGroupName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBoundaryGroupRelationship [-DisableWildcardHandling] [-FallbackDPMinutes <Int32>] [-FallbackMPMinutes <Int32>] [-FallbackSmpMinutes <Int32>] [-FallbackSupMinutes <Int32>] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
