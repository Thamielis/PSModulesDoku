Set-CMConfigurationItem
-----------------------




### Synopsis
Changes settings for a Configuration Manager configuration item.



---


### Description

The Set-CMConfigurationItem cmdlet changes settings for a Configuration Manager configuration item.



Configuration items contain one or more settings, along with compliance rules. Items usually define a unit of configuration you want to monitor. For more information about configuration items, see Introduction to Compliance Settings in Configuration Manager (/mem/configmgr/compliance/understand/ensure-device-compliance).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Introduction to Compliance Settings in Configuration Manager](Introduction to Compliance Settings in Configuration Manager)



* [Get-CMConfigurationItem](Get-CMConfigurationItem)



* [Get-CMConfigurationItemXMLDefinition](Get-CMConfigurationItemXMLDefinition)



* [Get-CMConfigurationItemHistory](Get-CMConfigurationItemHistory)



* [New-CMConfigurationItem](New-CMConfigurationItem)



* [Remove-CMConfigurationItem](Remove-CMConfigurationItem)



* [Import-CMConfigurationItem](Import-CMConfigurationItem)



* [Export-CMConfigurationItem](Export-CMConfigurationItem)



* [ConvertTo-CMConfigurationItem](ConvertTo-CMConfigurationItem)



* [ConvertFrom-CMConfigurationItem](ConvertFrom-CMConfigurationItem)





---


### Examples
#### Example 1: Change the name of a configuration item
```PowerShell
PS XYZ:\> Set-CMConfigurationItem -Name "CITest" -NewName "CITest01"
```
This command changes the name of the configuration item named CITest to CITest01.
#### Example 2: Set item settings
```PowerShell
PS XYZ:\> Set-CMConfigurationItem -Name "CITest01" -SecurityScopeAction AddMembership -SecurityScopeName "DefaultScope"
```
This command sets the security scope action to AddMembership and the security scope name to DefaultScope for the item named CITest01.
#### Example 3: Change item settings
```PowerShell
PS XYZ:\> Set-CMConfigurationItem -Name "CITest01" -SecurityScopeAction RemoveMembership -SecurityScopeName "DefaultScope"
```
This command sets the security scope action to RemoveMembership and the security scope name to DefaultScope for the item named CITest01.


---


### Parameters
#### **AddCategory**

Specifies an array of localized names of the categories to which the configuration item belongs.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **Description**

Specifies a description for a configuration item.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



#### **Digest**

Specifies the Digest that contain the configuration item.






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[ConfigurationItem]`|false   |named   |False        |



#### **DigestPath**

Specifies the path of the Digest.






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|false   |named   |False        |DesiredConfigurationDigestPath|



#### **DigestXml**

Specifies the XML definition.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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

Specifies an array of names for configuration items.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **NewName**

Specifies a new name for a configuration item.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Returns the current working object. By default, this cmdlet does not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveCategory**

Specifies an array of localized names of the categories from which to remove the configuration item.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



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
Set-CMConfigurationItem [-Id] <Int32> [-AddCategory <String[]>] [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveCategory <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMConfigurationItem [-InputObject] <IResultObject> [-AddCategory <String[]>] [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveCategory <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMConfigurationItem [-Name] <String> [-AddCategory <String[]>] [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveCategory <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
