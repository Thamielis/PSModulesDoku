Get-CMMigrationCollection
-------------------------




### Synopsis
Gets collections selected for migration.



---


### Description

The Get-CMMigrationCollection cmdlet gets the collections selected from a source hierarchy for migration. A collection is a set of resources in the Configuration Manager hierarchy. A migration collection is the set of resources chosen from a hierarchy for migration, including related objects.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Get a migration collection by name
```PowerShell
PS XYZ:\> Get-CMMigrationCollection -Name "PhoneCollection5"
```
This command gets the migration collection. The command specifies the value PhoneCollection5 for the Name parameter.


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

Specifies an identifier for a collection in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|false   |named   |False        |CollectionEntityId|



#### **Name**

Specifies a name for a collection in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |CollectionName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_MigrationCollectionInfo


* IResultObject#SMS_MigrationCollectionInfo






---


### Notes




---


### Syntax
```PowerShell
Get-CMMigrationCollection [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [<CommonParameters>]
```
```PowerShell
Get-CMMigrationCollection [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
