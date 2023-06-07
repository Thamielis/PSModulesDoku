Get-CMMigrationEntity
---------------------




### Synopsis
Gets a migration entity in Configuration Manager.



---


### Description

The Get-CMMigrationEntity cmdlet gets the migration entity in Configuration Manager. A migration entity is an object to be migrated that is of any type that is supported by migration.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMMigrationEntityDependency](Get-CMMigrationEntityDependency)



* [New-CMMigrationJob](New-CMMigrationJob)





---


### Examples
#### Example 1: Get information about all your migration entities
```PowerShell
PS XYZ:\> Get-CMMigrationEntity
```
This command returns information about all of your migration entities.
#### Example 2: Get information about a specific migration entity
```PowerShell
PS XYZ:\> Get-CMMigrationEntity -Name "MigrationTest"
```
This command returns information about the migration entity with the name MigrationTest.
#### Example 3: Get information about active migration entities
```PowerShell
PS XYZ:\> Get-CMMigrationEntity -IsActive
```
This command returns information about all of your active migration entities.


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

Specifies an identifier in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |EntityId|



#### **IsActive**

Specifies that this migration entity is active.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specifies a name in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |EntityName|



#### **Type**

Specifies a type in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_MigrationEntity


* IResultObject#SMS_MigrationEntity






---


### Notes




---


### Syntax
```PowerShell
Get-CMMigrationEntity [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [<CommonParameters>]
```
```PowerShell
Get-CMMigrationEntity [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsActive <String>] [-Type <String>] [<CommonParameters>]
```
```PowerShell
Get-CMMigrationEntity [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
