Get-CMComputerAssociation
-------------------------




### Synopsis
Gets Configuration Manager computer associations.



---


### Description

The Get-CMComputerAssociation cmdlet gets computer associations. Configuration Manager uses a computer association to migrate user state and settings as part of operating system deployment. You can specify a source computer, a destination computer, or both. You can also use an ID to specify a computer association.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMComputerAssociation](New-CMComputerAssociation)



* [Remove-CMComputerAssociation](Remove-CMComputerAssociation)



* [Set-CMComputerAssociation](Set-CMComputerAssociation)





---


### Examples
#### Example 1: Get all computer associations
```PowerShell
PS XYZ:\> Get-CMComputerAssociation
```
This command gets all the computer associations for Configuration Manager.
#### Example 2: Get computer associations for a destination comptuter
```PowerShell
PS XYZ:\> Get-CMComputerAssociation -DestinationComputer "West155"
```
This command gets all the computer associations for the destination computer named West155.
#### Example 3: Get a computer association by using an ID
```PowerShell
PS XYZ:\> Get-CMComputerAssociation -MigrationId "MID1207"
```
This command gets the computer association that has the ID MID1207.


---


### Parameters
#### **DestinationComputer**

Specifies the name of a destination computer.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |RestoreName|



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



#### **MigrationId**

Specifies the ID of a computer association.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SourceComputer**

Specifies the name of a source computer.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |SourceName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_StateMigration


* IResultObject#SMS_StateMigration






---


### Notes




---


### Syntax
```PowerShell
Get-CMComputerAssociation [-DestinationComputer <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SourceComputer <String>] [<CommonParameters>]
```
```PowerShell
Get-CMComputerAssociation [-DisableWildcardHandling] [-ForceWildcardHandling] -MigrationId <String> [<CommonParameters>]
```
