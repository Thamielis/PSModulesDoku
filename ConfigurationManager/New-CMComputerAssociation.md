New-CMComputerAssociation
-------------------------




### Synopsis
Creates an association between two computers in Configuration Manager.



---


### Description

The New-CMComputerAssociation cmdlet creates an association between two computers to use for migration. Configuration Manager can migrate user state and settings from an existing computer to a different computer as part of operating system deployment. In the course of migration, Configuration Manager saves accounts created on the source computer and creates those user accounts on the destination computer.



To create an association, specify the source computer, the destination computer, and at least one user name created on the source computer to be migrated. You can also specify whether the migration includes other user names from the source computer.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMComputerAssociation](Get-CMComputerAssociation)



* [Remove-CMComputerAssociation](Remove-CMComputerAssociation)



* [Set-CMComputerAssociation](Set-CMComputerAssociation)





---


### Examples
#### Example 1: Create a computer association
```PowerShell
PS XYZ:\> New-CMComputerAssociation -SourceComputer "TSQA073" -MigrationUserName "Contoso-TSQA\ElisaDaugherty" -DestinationComputer "TSQA155"
```
This command creates a computer association between the source computer named TSQA073 and the destination computer named TSQA155. The command specifies a user name for migration to the destination computer.


---


### Parameters
#### **DestinationComputer**

Specifies the name of a destination computer.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |RestoreName|



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



#### **MigrationBehavior**

Specifies how Configuration Manager treats user accounts created on the source computer. When you create a computer association, specify user accounts created on the source computer by using the MigrationUserName parameter. The computer association can specify that the migration process creates some or all of those accounts on the destination computer.


The acceptable values for this parameter are:


* CaptureAllUserAccountsAndRestoreSpecifiedAccounts. Saves all accounts created on the source computer, but creates only the specified accounts on the destination computer. - CaptureAndRestoreAllUserAccounts. Saves all accounts created on the source computer, and creates them on the destination computer. - CaptureAndRestoreSpecifiedUserAccounts. Saves only the specified accounts from the source computer, and creates those accounts on the destination computer.


If you do not specify a migration behavior, the migration uses CaptureAndRestoreAllUserAccounts.



Valid Values:

* CaptureAndRestoreAllUserAccounts
* CaptureAllUserAccountsAndRestoreSpecifiedAccounts
* CaptureAndRestoreSpecifiedUserAccounts






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[MigrationBehavior]`|false   |named   |False        |



#### **MigrationUserName**

Specifies an array of user names for accounts created on the source computer. The specified user names, along with the MigrationBehavior parameter setting, determine which user accounts Configuration Manager creates on the destination computer.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **SourceComputer**

Specifies the name of the source computer.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |SourceName|



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
* IResultObject#SMS_StateMigration






---


### Notes




---


### Syntax
```PowerShell
New-CMComputerAssociation -DestinationComputer <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-MigrationBehavior {CaptureAndRestoreAllUserAccounts | CaptureAllUserAccountsAndRestoreSpecifiedAccounts | CaptureAndRestoreSpecifiedUserAccounts}] [-MigrationUserName <String[]>] -SourceComputer <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
