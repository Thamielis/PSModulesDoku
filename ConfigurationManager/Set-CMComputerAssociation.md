Set-CMComputerAssociation
-------------------------




### Synopsis
Changes settings for a computer association in Configuration Manager.



---


### Description

The Set-CMComputerAssociation cmdlet changes settings for a computer association used for migration. Configuration Manager can migrate user state and settings from an existing computer to a different computer as part of operating system deployment. In the course of migration, Configuration Manager saves accounts created on the source computer and creates those user accounts on the destination computer.



A computer association contains the user names to be migrated and how to deal with other user names from the source computer. You can use this cmdlet to modify an association. You can add user names to the association, or remove user names. You can also change whether Configuration Manager includes other user names from the source computer.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMComputerAssociation](Get-CMComputerAssociation)



* [New-CMComputerAssociation](New-CMComputerAssociation)



* [Remove-CMComputerAssociation](Remove-CMComputerAssociation)





---


### Examples
#### Example 1: Modify a computer association
```PowerShell
PS XYZ:\> Set-CMComputerAssociation -DestinationComputer "TSQA155" -SourceComputer "TSQA073" -AddMigrationUserName "ContosoTSQA\EvanNarvaez" -MigrationBehavior CaptureAllUserAccountsAndRestoreSpecifiedAccounts -RemoveMigrationUserName "ContosoTSQA\ElisaDaugherty"
```
This command changes the association between the computer named TSQA073 and TSQA155. The command adds the user ContosoTSQA\EvanNarvaez and removes the user ContosoTSQA\ElisaDaugherty. The command specifies the migration behavior as CaptureAllUserAccountsAndRestoreSpecifiedAccounts, so the association causes the migration to save all accounts created on the source computer, but only to create the accounts specified by the computer association on the destination computer.


---


### Parameters
#### **AddMigrationUserName**

Specifies an array of user names for accounts created on the source computer. The cmdlet adds these user names to the current specified user names of the computer association.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



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

Specifies how Configuration Manager treats user accounts created on the source computer. When you create a computer association, specify user accounts created on the source computer by using the MigrationUserName parameter of the New-CMComputerAssociation (New-CMComputerAssociation.md)cmdlet. The computer association can specify that the migration process creates some or all of those accounts on the destination computer.


The acceptable values for this parameter are:


* CaptureAllUserAccountsAndRestoreSpecifiedAccounts. Saves all accounts created on the source computer, but creates only the specified accounts on the destination computer. - CaptureAndRestoreAllUserAccounts. Saves all accounts created on the source computer, and creates them on the destination computer. - CaptureAndRestoreSpecifiedUserAccounts. Saves only the specified accounts from the source computer, and creates those accounts on the destination computer.



Valid Values:

* CaptureAndRestoreAllUserAccounts
* CaptureAllUserAccountsAndRestoreSpecifiedAccounts
* CaptureAndRestoreSpecifiedUserAccounts






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[MigrationBehavior]`|false   |named   |False        |



#### **MigrationId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RemoveMigrationUserName**

Specifies an array of user names for accounts created on the source computer. The cmdlet removes these user names from current specified user names of the computer association.






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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMComputerAssociation [-AddMigrationUserName <String[]>] -DestinationComputer <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-MigrationBehavior {CaptureAndRestoreAllUserAccounts | CaptureAllUserAccountsAndRestoreSpecifiedAccounts | CaptureAndRestoreSpecifiedUserAccounts}] [-RemoveMigrationUserName <String[]>] -SourceComputer <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMComputerAssociation [-AddMigrationUserName <String[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MigrationBehavior {CaptureAndRestoreAllUserAccounts | CaptureAllUserAccountsAndRestoreSpecifiedAccounts | CaptureAndRestoreSpecifiedUserAccounts}] -MigrationId <String> [-RemoveMigrationUserName <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
