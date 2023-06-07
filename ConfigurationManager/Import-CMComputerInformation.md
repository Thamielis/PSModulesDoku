Import-CMComputerInformation
----------------------------




### Synopsis
Imports computer information into a Configuration Manager database.



---


### Description

The Import-CMComputerInformation cmdlet imports computer information directly into a Configuration Manager database. For Configuration Manager to deploy an operating system to a new computer with no installed operating system, you must add the new computer to Configuration Manager. After you import the computer information, Configuration Manager can deploy an operating system.



You can import a single computer by specifying the Media Access Control (MAC) address and computer name, along with the name of a collection. This cmdlet adds this computer to the specified collection.



You can also import several computers by specifying a Comma Separated Values .csv file with computer information, along with the name of a collection. This cmdlet adds the computers to the specified collection.



You can specify the name of a reference computer. Configuration Manager migrates user information and settings from the reference computer to the new computer.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMComputerAssociation](Get-CMComputerAssociation)





---


### Examples
#### Example 1: Import computers by using a file
```PowerShell
PS XYZ:\>Import-CMComputerInformation -CollectionName "All Systems" -FileName "\\cmshare\Public\CM\ImportComputers.csv" -EnableColumnHeading $True
```
This command imports the computers specified in the CSV file into the All Systems collection. This command includes a value of $True for the -EnableColumnHeading parameter. The cmdlet ignores the first line of the file.
#### Example 2: Import a single computer
```PowerShell
PS XYZ:\>Import-CMComputerInformation -CollectionName "All Systems" -ComputerName "Computer08" -MacAddress "5F:DA:FA:FA:FA:FA" -SmBiosGuid "AAAAAAAA-AAAA-AAAA-AAAA-AAAAAAAAAAAA"
```
This command imports a specified computer into the All Systems collection. The command specifies the name, MAC address, and SMBIOS GUID for a computer.
#### Example 3: Import a computer using a reference computer
```PowerShell
PS XYZ:\>Import-CMComputerInformation -CollectionName "All Systems" -ComputerName "Computer08" -MacAddress "5F:DA:FA:FA:FA:FA" -SmBiosGuid "AAAAAAAA-AAAA-AAAA-AAAA-AAAAAAAAAAAA" -SourceComputerName "ResourceComputer01"
```
This command imports a specified computer into the All Systems collection. The command specifies the name, MAC address, and SMBIOS GUID for a computer. The command also includes a reference computer to associate with the new computer.


---


### Parameters
#### **CollectionId**








|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |CollectionIds|



#### **CollectionName**

Specifies a name of a Configuration Manager device collection.






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|false   |named   |False        |CollectionNames|



#### **ComputerName**

Specifies the name of a computer that this cmdlet imports information from.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableColumnHeading**








|Type       |Required|Position|PipelineInput|Aliases             |
|-----------|--------|--------|-------------|--------------------|
|`[Boolean]`|false   |named   |False        |EnableColumnHeadings|



#### **FileName**

Specifies a .csv file that contains computer information. The file must contain the name and MAC address of each computer to be imported.






|Type      |Required|Position|PipelineInput|Aliases                             |
|----------|--------|--------|-------------|------------------------------------|
|`[String]`|true    |named   |False        |FilePath<br/>ImportFilePath<br/>Path|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type               |Required|Position|PipelineInput |Aliases                   |
|-------------------|--------|--------|--------------|--------------------------|
|`[IResultObject[]]`|false   |named   |True (ByValue)|Collection<br/>Collections|



#### **MacAddress**

Specifies a MAC address for a computer in the format (00:00:00:00:00:00). The Windows Preinstallation Environment (Windows PE) must have a driver for the specified network adapter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MergeIfExist**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SMBiosGuid**

Specifies a GUID for the system management BIOS (SMBIOS) of a computer.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |SMBIOSID|



#### **SourceComputerName**

Specifies a name of a reference computer. Configuration Manager migrates user state and settings from the reference computer to the new computer.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserAccountMigrationBehavior**





Valid Values:

* CaptureAllUserAccountsAndRestoreSpecifiedAccounts
* CaptureAndRestoreSpecifiedUserAccounts






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[MigrationBehavior]`|false   |named   |False        |



#### **UserName**








|Type        |Required|Position|PipelineInput|Aliases  |
|------------|--------|--------|-------------|---------|
|`[String[]]`|false   |named   |False        |UserNames|



#### **VariableName**

Specifies a variable name for an imported column. When you import a .csv file, you specify the columns to import and assign them to a Configuration Manager field. A variable allows you to assign a column to a variable.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **WindowsToGoUniqueKey**








|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |WtgUniqueKey|



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Import-CMComputerInformation [-CollectionId <String[]>] [-CollectionName <String[]>] -ComputerName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IResultObject[]>] [-MacAddress <String>] [-MergeIfExist] [-SMBiosGuid <String>] [-SourceComputerName <String>] [-UserAccountMigrationBehavior {CaptureAllUserAccountsAndRestoreSpecifiedAccounts | CaptureAndRestoreSpecifiedUserAccounts}] [-UserName <String[]>] [-WindowsToGoUniqueKey <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Import-CMComputerInformation [-CollectionId <String[]>] [-CollectionName <String[]>] [-DisableWildcardHandling] [-EnableColumnHeading <Boolean>] -FileName <String> [-ForceWildcardHandling] [-InputObject <IResultObject[]>] [-VariableName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
