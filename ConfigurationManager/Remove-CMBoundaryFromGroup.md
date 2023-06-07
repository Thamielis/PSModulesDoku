Remove-CMBoundaryFromGroup
--------------------------




### Synopsis
Removes a Configuration Manager boundary from a boundary group.



---


### Description

The Remove-CMBoundaryFromGroup cmdlet removes a Configuration Manager boundary from a boundary group. A boundary is a network address range, subnet, or Active Directory site that identifies a group of computers that are close in the network. A boundary group is a collection of boundaries.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMBoundaryToGroup](Add-CMBoundaryToGroup)



* [Get-CMBoundary](Get-CMBoundary)



* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)



* [New-CMBoundary](New-CMBoundary)



* [New-CMBoundaryGroup](New-CMBoundaryGroup)



* [Remove-CMBoundary](Remove-CMBoundary)



* [Remove-CMBoundaryGroup](Remove-CMBoundaryGroup)



* [Set-CMBoundaryGroup](Set-CMBoundaryGroup)





---


### Examples
#### Example 1: Remove a boundary from a group by using the boundary name
```PowerShell
PS XYZ:\> Remove-CMBoundaryFromGroup -BoundaryGroupID "16777219" -BoundaryName "CLBound03"
```
This example removes a boundary named CLBound03 from a boundary group that has the ID 16777219.
#### Example 2: Remove multiple boundary groups by using an InputObject
```PowerShell
PS XYZ:\> $BoundaryObj = Get-CMBoundary -Name "Bound01", "Bound02", "Bound03"
PS XYZ:\> Remove-CMBoundaryFromGroup -Boundary $BoundaryObj -BoundaryGroupName "BGroup02"
```
The first command uses the Get-CMBoundary cmdlet to get multiple boundaries that are specified by their names, and stores this data into the $BoundaryObj variable.


The second command identifies and removes the boundaries that are specified by using the input object $BoundaryObj . Because the Force parameter is not specified, you must confirm the action before it is performed.


---


### Parameters
#### **BoundaryGroupId**

Specifies an ID for the boundary group from which you remove a boundary.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **BoundaryGroupInputObject**








|Type             |Required|Position|PipelineInput|Aliases      |
|-----------------|--------|--------|-------------|-------------|
|`[IResultObject]`|true    |named   |False        |BoundaryGroup|



#### **BoundaryGroupName**

Specifies a name for the boundary group from which you remove a boundary.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BoundaryId**

Specifies an ID for the boundary that this cmdlet removes.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **BoundaryInputObject**








|Type             |Required|Position|PipelineInput|Aliases |
|-----------------|--------|--------|-------------|--------|
|`[IResultObject]`|true    |named   |False        |Boundary|



#### **BoundaryName**

Specifies a name for the boundary that this cmdlet removes.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMBoundaryFromGroup -BoundaryGroupId <Int32> -BoundaryId <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryFromGroup -BoundaryGroupId <Int32> -BoundaryName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryFromGroup -BoundaryGroupId <Int32> -BoundaryInputObject <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryFromGroup -BoundaryGroupInputObject <IResultObject> -BoundaryId <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryFromGroup -BoundaryGroupInputObject <IResultObject> -BoundaryName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryFromGroup -BoundaryGroupInputObject <IResultObject> -BoundaryInputObject <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryFromGroup -BoundaryGroupName <String> -BoundaryId <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryFromGroup -BoundaryGroupName <String> -BoundaryName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryFromGroup -BoundaryGroupName <String> -BoundaryInputObject <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
