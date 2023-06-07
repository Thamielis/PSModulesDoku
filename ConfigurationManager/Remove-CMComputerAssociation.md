Remove-CMComputerAssociation
----------------------------




### Synopsis
Deletes a computer association from Configuration Manager.



---


### Description

The Remove-CMComputerAssociation cmdlet deletes a computer association from Configuration Manager. You can specify the association to remove by specifying both computers in the association or by specifying the association ID, or you can use the Get-CMComputerAssociation cmdlet to get an association to remove.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMComputerAssociation](Get-CMComputerAssociation)



* [New-CMComputerAssociation](New-CMComputerAssociation)



* [Set-CMComputerAssociation](Set-CMComputerAssociation)





---


### Examples
#### Example 1: Remove an association by using computer names
```PowerShell
PS XYZ:\> Remove-CMComputerAssociation -DestinationComputer "West155" -SourceComputer "West073"
```
This command removes the computer association between the computers named West155 and West073.
#### Example 2: Remove an association by using an ID
```PowerShell
PS XYZ:\> Remove-CMComputerAssociation -MigrationId "MID1207" -Force
```
This command removes the computer association that has the ID MID1207. This command uses the Force parameter, so the cmdlet does not prompt you for confirmation before it removes the association.
#### Example 3: Remove an association by using a variable
```PowerShell
PS XYZ:\> $CMCA = Get-CMComputerAssociation -MigrationId "MID1207"
PS XYZ:\> Remove-CMComputerAssociation -InputObject $CMCA -Force
```
The first command gets the computer association that has the ID MID1207, and saves it in the $CMCA variable.


The second command removes the association saved in the $CMCA variable. This command uses the Force parameter, so the cmdlet does not prompt you for confirmation before it removes the association.


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



#### **InputObject**

Specifies a computer association object. To obtain a computer association object, use the Get-CMComputerAssociation cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **MigrationId**

Specifies the ID of a computer association.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Remove-CMComputerAssociation -DestinationComputer <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -SourceComputer <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMComputerAssociation [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMComputerAssociation [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -MigrationId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
