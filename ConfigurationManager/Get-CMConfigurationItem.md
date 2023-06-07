Get-CMConfigurationItem
-----------------------




### Synopsis
Gets Configuration Manager configuration items.



---


### Description

The Get-CMConfigurationItem cmdlet gets configuration item objects in Configuration Manager. You can use this cmdlet to get items for other cmdlets to use. For instance, you might get configuration items so you can use the Set-CMConfigurationItem to change settings on them.



Configuration items contain one or more settings, along with compliance rules. For more information about configuration items, see Introduction to Compliance Settings in Configuration Manager (/mem/configmgr/compliance/understand/ensure-device-compliance).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Introduction to Compliance Settings in Configuration Manager](Introduction to Compliance Settings in Configuration Manager)



* [Get-CMConfigurationItemXMLDefinition](Get-CMConfigurationItemXMLDefinition)



* [Get-CMConfigurationItemHistory](Get-CMConfigurationItemHistory)



* [New-CMConfigurationItem](New-CMConfigurationItem)



* [Set-CMConfigurationItem](Set-CMConfigurationItem)



* [Remove-CMConfigurationItem](Remove-CMConfigurationItem)



* [Import-CMConfigurationItem](Import-CMConfigurationItem)



* [Export-CMConfigurationItem](Export-CMConfigurationItem)



* [ConvertTo-CMConfigurationItem](ConvertTo-CMConfigurationItem)



* [ConvertFrom-CMConfigurationItem](ConvertFrom-CMConfigurationItem)





---


### Examples
#### Example 1: Get an item using a name
```PowerShell
PS XYZ:\> Get-CMConfigurationItem -Name "ConfigItem76"
```
This command gets a configuration item named ConfigItem76.
#### Example 2: Get an item to use with another cmdlet
```PowerShell
PS XYZ:\> $CIObj=Get-CMConfigurationItem -Id "16777568"
PS XYZ:\> Remove-CMConfigurationItem -InputObject $CIObj
```
The first command gets a configuration item with the specified identifier and stores it in the $CIObj variable.


The second command removes the item in the $CIObj variable.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Indicates that the cmdlet does not automatically refresh lazy properties.


Lazy properties contain values that are relatively inefficient to retrieve which can cause additional network traffic and decrease cmdlet performance. If lazy properties are not needed, this parameter should be specified.






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



#### **Name**

Specifies an array of names of configuration items. You can use a comma separated list.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |0       |False        |LocalizedDisplayName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_ConfigurationItemLatest


* IResultObject#SMS_ConfigurationItemLatest






---


### Notes




---


### Syntax
```PowerShell
Get-CMConfigurationItem [-Id] <Int32> [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationItem [[-Name] <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
