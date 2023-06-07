Remove-CMBoundaryGroup
----------------------




### Synopsis
Removes a boundary group.



---


### Description

The Remove-CMBoundaryGroup cmdlet removes a boundary group from Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)



* [New-CMBoundaryGroup](New-CMBoundaryGroup)



* [Set-CMBoundaryGroup](Set-CMBoundaryGroup)





---


### Examples
#### Example 1: Remove a boundary group that is specified by its ID
```PowerShell
PS XYZ:\> Remove-CMBoundaryGroup -Id "16777219"
```
This command removes a boundary group that is specified by its identifier. Because the Force parameter is not specified, you must confirm the action before it is performed.
#### Example 2: Remove multiple boundary groups by using an InputObject
```PowerShell
PS XYZ:\> $BoundaryObj = Get-CMBoundary -Name "BGroup01", "BGroup02", "BGroup03"
PS XYZ:\> Remove-CMBoundary -InputObject $BoundaryObj
```
The first command uses the Get-CMBoundaryGroup to get multiple boundary groups that are specified by their names, and stores this data into the $BoundaryObj variable.


The second command identifies and removes the boundaries that are specified by using the input object $BoundaryObj. Because the Force parameter is not specified, you must confirm the action before it is performed.


---


### Parameters
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



#### **Id**

Specifies an array of identifiers (IDs) for one or more boundary groups.






|Type        |Required|Position|PipelineInput|Aliases|
|------------|--------|--------|-------------|-------|
|`[String[]]`|true    |named   |False        |GroupId|



#### **InputObject**

Specifies an input object to this cmdlet. You can get the input object by using the Get-CMBoundaryGroup (Get-CMBoundaryGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies the name of a boundary group.






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
* 






---


### Notes




---


### Syntax
```PowerShell
Remove-CMBoundaryGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBoundaryGroup [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
