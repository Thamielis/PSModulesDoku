Add-CMBoundaryToGroup
---------------------




### Synopsis
Assigns boundaries to a boundary group in Configuration Manager.



---


### Description

The Add-CMBoundaryToGroup cmdlet assigns boundaries to a boundary group.



In Configuration Manager, a boundary is an intranet location that contains one or more devices that you can manage. A boundary can be an IP subnet, Active Directory site name, IPv6 prefix, or an IP address range.



You can use boundary groups to manage network locations. You must assign boundaries to boundary groups before you can use the boundary group. Boundary groups enable client computers to find a primary site for client assignment, which is referred to as automatic site assignment, and a list of available site systems that have content. For more information about boundaries, see Planning for Boundaries and Boundary Groups in Configuration Manager (/mem/configmgr/core/servers/deploy/configure/define-site-boundaries-and-boundary-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Planning for Boundaries and Boundary Groups in Configuration Manager](Planning for Boundaries and Boundary Groups in Configuration Manager)



* [Get-CMBoundary](Get-CMBoundary)



* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)



* [Remove-CMBoundaryFromGroup](Remove-CMBoundaryFromGroup)





---


### Examples
#### Example 1: Assign a boundary group to a boundary
```PowerShell
PS XYZ:\>Add-CMBoundaryToGroup -BoundaryGroupID "16777219" -BoundaryName "CLBound03"
```
This command assigns the boundary named to CLBound03 to the boundary group that has the Id 16777219.


---


### Parameters
#### **BoundaryGroupId**

Specifies the ID of a boundary group.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **BoundaryGroupInputObject**








|Type             |Required|Position|PipelineInput|Aliases      |
|-----------------|--------|--------|-------------|-------------|
|`[IResultObject]`|true    |named   |False        |BoundaryGroup|



#### **BoundaryGroupName**

Specifies the name of a boundary group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BoundaryId**

Specifies the ID of a boundary.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **BoundaryName**

Specifies the name of a boundary.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                         |
|-----------------|--------|--------|--------------|--------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Boundary<br/>BoundaryInputObject|



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
Add-CMBoundaryToGroup -BoundaryGroupId <Int32> -BoundaryId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMBoundaryToGroup -BoundaryGroupId <Int32> -BoundaryName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMBoundaryToGroup -BoundaryGroupId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMBoundaryToGroup -BoundaryGroupInputObject <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMBoundaryToGroup -BoundaryGroupInputObject <IResultObject> -BoundaryId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMBoundaryToGroup -BoundaryGroupInputObject <IResultObject> -BoundaryName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMBoundaryToGroup -BoundaryGroupName <String> -BoundaryId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMBoundaryToGroup -BoundaryGroupName <String> -BoundaryName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMBoundaryToGroup -BoundaryGroupName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
