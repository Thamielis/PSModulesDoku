Resolve-CMInventoriedSoftwareConflict
-------------------------------------




### Synopsis
Resolves a conflict in Configuration Manager software inventory information.



---


### Description

The Resolve-CMInventoriedSoftwareConflict cmdlet resolves a conflict in Configuration Manager software inventory information.



When Configuration Manager receives updated information about software that is part of the software inventory, that information may conflict with your local settings. You can resolve a conflict by keeping your local inventory information or updating to the new information.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareInventory](Get-CMSoftwareInventory)



* [Set-CMSoftwareInventory](Set-CMSoftwareInventory)



* [Undo-CMSoftwareInventory](Undo-CMSoftwareInventory)





---


### Examples
#### Example 1: Resolve a software conflict and keep local inventory information
```PowerShell
PS XYZ:\> Resolve-CMInventoriedSoftwareConflict -Id "SMS0001" -RevertLocalEdit $True
```
This command resolves a software conflict that has the specified ID. The command keeps the current, local version of the conflicting information.


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

Specifies an array of IDs for conflicts in software inventory.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |SoftwareKey|



#### **RevertLocalEdit**

Indicates whether this cmdlet keeps the current inventory information for the conflict or updates that information. If this parameter is $True, the cmdlet keeps current, local information. If this parameter is $False, the cmdlet replaces conflicting information with updated information.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|true    |named   |False        |



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Resolve-CMInventoriedSoftwareConflict [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> -RevertLocalEdit <Boolean> [-Confirm] [-WhatIf] [<CommonParameters>]
```
