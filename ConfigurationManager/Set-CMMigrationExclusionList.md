Set-CMMigrationExclusionList
----------------------------




### Synopsis
Edits the global exclusion list for migration jobs.



---


### Description

The Set-CMMigrationExclusionList cmdlet edits the global exclusion list for migration jobs in Configuration Manager.



For a collection-based migration, you specify one or more collections to migrate. For each collection that you specify, the migration job automatically selects all related objects for migration. Objects on the exclusion list are available for migration, but Configuration Manager does not automatically include these objects when you create a new collection-based migration job.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Clear-CMMigrationData](Clear-CMMigrationData)



* [Set-CMMigrationSource](Set-CMMigrationSource)





---


### Examples
#### Example 1: Specify a migration exclusion list
```PowerShell
PS XYZ:\> Set-CMMigrationExclusionList -Name "ContosoUsersWest01"
```
This command adds the objects in the array ContosoUsersWest01 to the migration exclusion list.


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



#### **Name**

Specifies an array of objects that you exclude by default from collection-based migration jobs.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |EntityName|



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
Set-CMMigrationExclusionList [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
