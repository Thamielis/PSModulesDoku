Import-CMConfigurationItem
--------------------------




### Synopsis
Imports Configuration Manager configuration items.



---


### Description

The Import-CMConfigurationItem cmdlet imports Configuration Manager configuration items from one or more cabinet files. The files that you import must conform to the Service Modeling Language (SML) schema and can contain information about configuration data from one of the following sources:



- Best practices from a Configuration Manager Configuration Pack.



- Configuration data that you have externally authored and packaged into a cabinet (.cab) file.



- Configuration data exported from Configuration Manager.






Configuration items contain one or more settings, along with compliance rules. Items usually define a unit of configuration you want to monitor.


> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).




---


### Related Links
* [Introduction to Compliance Settings in Configuration Manager](Introduction to Compliance Settings in Configuration Manager)



* [Get-CMConfigurationItem](Get-CMConfigurationItem)



* [Get-CMConfigurationItemXMLDefinition](Get-CMConfigurationItemXMLDefinition)



* [Get-CMConfigurationItemHistory](Get-CMConfigurationItemHistory)



* [New-CMConfigurationItem](New-CMConfigurationItem)



* [Set-CMConfigurationItem](Set-CMConfigurationItem)



* [Remove-CMConfigurationItem](Remove-CMConfigurationItem)



* [Export-CMConfigurationItem](Export-CMConfigurationItem)



* [ConvertTo-CMConfigurationItem](ConvertTo-CMConfigurationItem)



* [ConvertFrom-CMConfigurationItem](ConvertFrom-CMConfigurationItem)





---


### Examples
#### Example 1: Import configuration items
```PowerShell
PS XYZ:\>Import-CMConfigurationItem -FileName "\\atc-dist-01\Public\CM\AdminUITeam\CIData\7389_OSCI.cab","\\atc-dist-01\Public\CM\AdminUITeam\CIData\7452OS_1.cab"
```
This command imports configuration items from the files 7389_OSCI.cab and 7452OS_1.cab.
#### Example 2: Import configuration items and create duplicate configuration items
```PowerShell
PS XYZ:\>Import-CMConfigurationItem -FileName "\\Contoso01\Public\CM\7389_OSCI.cab","\\ Contoso01\Public\CM\7452OS_1.cab" -DuplicateWhileImporting
```
This command imports configuration items from the files 7389_OSCI.cab and 7452OS_1.cab. The DuplicateWhileImporting parameter indicates that imports configuration items that exist in Configuration Manager as duplicate configuration items.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DuplicateWhileImporting**

Indicates that Configuration Manager imports configuration items that exist in Configuration Manager as duplicate configuration items.


Use this parameter to create a configuration item when you want an exact copy of a configuration item that you import to use as your starting point, but you want to modify it to create an independent configuration item from the original.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileName**

Specifies an array of names of cabinet (cab) files.






|Type        |Required|Position|PipelineInput|Aliases                                                                                       |
|------------|--------|--------|-------------|----------------------------------------------------------------------------------------------|
|`[String[]]`|true    |named   |False        |FilePath<br/>ImportFilePath<br/>Path<br/>FileNames<br/>FilePaths<br/>ImportFilePaths<br/>Paths|



#### **Force**

Forces the command to run without asking for user confirmation.


Use this parameter to create a configuration item when you want an exact copy of a configuration item that you import to use as your starting point, but you want to modify it to create an independent configuration item from the original.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .


Use this parameter to create a configuration item when you want an exact copy of a configuration item that you import to use as your starting point, but you want to modify it to create an independent configuration item from the original.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Import-CMConfigurationItem [-DisableWildcardHandling] [-DuplicateWhileImporting] -FileName <String[]> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
