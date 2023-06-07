Export-CMConfigurationItem
--------------------------




### Synopsis
Saves a Configuration Manager configuration item to a file.



---


### Description

The Export-CMConfigurationItem cmdlet saves a Configuration Manager configuration item to a specified .cab file. You can specify items by ID, name, or by use of the Get-CMConfigurationItem (Get-CMConfigurationItem.md)cmdlet.



Configuration items contain one or more settings, along with compliance rules. For more information about configuration items, see Introduction to Compliance Settings in Configuration Manager (/mem/configmgr/compliance/understand/ensure-device-compliance).



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



* [Import-CMConfigurationItem](Import-CMConfigurationItem)



* [ConvertTo-CMConfigurationItem](ConvertTo-CMConfigurationItem)



* [ConvertFrom-CMConfigurationItem](ConvertFrom-CMConfigurationItem)





---


### Examples
#### Example 1: Export an item using an ID
```PowerShell
PS XYZ:\>Export-CMConfigurationItem -Id "16777568" -Path "C:\Exports\CI16777568.cab"
```
This command exports a configuration item with the identifier named 16777568 to the specified file.
#### Example 2: Export an item using a name
```PowerShell
PS XYZ:\>Export-CMConfigurationItem -Name "ConfigItem76" -Path "C:\Exports\CIConfigItem76.cab"
```
This command exports a configuration item named ConfigItem76 to the specified file.
#### Example 3: Export an item using a variable
```PowerShell
PS XYZ:\> $CIObj=Get-CMConfigurationItem -Id "16777568"
PS XYZ:\> Export-CMConfigurationItem -InputObject $CIObj -Path "C:\Exports\CI16777568.cab"
```
The first command gets a configuration item with the specified identifier and stores it in the $CIObj variable.


The second command exports the item in the $CIObj variable to the specified file.


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

Specifies an array of identifiers for one or more configuration items. You can use a comma separated list.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a configuration item object. To obtain a configuration item object, you can use the Get-CMConfigurationItem (Get-CMConfigurationItem.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies an array of names of configuration items. You can use a comma separated list.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **Path**

Specifies a full file path for an export file.






|Type      |Required|Position|PipelineInput|Aliases                                 |
|----------|--------|--------|-------------|----------------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>ExportFilePath|



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
Export-CMConfigurationItem [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMConfigurationItem [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMConfigurationItem [-Name] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
