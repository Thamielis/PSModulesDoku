Get-CMMigrationEntityDependency
-------------------------------




### Synopsis
Gets a dependency for a migration entity in Configuration Manager.



---


### Description

The Get-CMMigrationEntityDependency cmdlet gets a migration entity dependency in Configuration Manager. A migration entity dependency is an object upon which another object to be migrated is dependent.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Get information about all migration entity dependencies
```PowerShell
PS XYZ:\> Get-CMMigrationEntityDependency
```
This command returns information about all your migration entity dependencies.
#### Example 2: Get information about a specific migration entity dependency
```PowerShell
PS XYZ:\> Get-CMMigrationEntityDependency -Id "121989"
```
This command returns information about the migration entity dependency that has the ID 121989.


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

Specifies an ID in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |EntityId|



#### **Type**

Specifies a type in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |DependencyType|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_MigrationEntityDependency


* IResultObject#SMS_MigrationEntityDependency






---


### Notes




---


### Syntax
```PowerShell
Get-CMMigrationEntityDependency [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [<CommonParameters>]
```
```PowerShell
Get-CMMigrationEntityDependency [-DisableWildcardHandling] [-ForceWildcardHandling] [-Type <String>] [<CommonParameters>]
```
