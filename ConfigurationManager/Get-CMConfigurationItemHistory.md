Get-CMConfigurationItemHistory
------------------------------




### Synopsis
Gets the previous versions of a configuration item in Configuration Manager.



---


### Description

The Get-CMConfigurationItemHistory cmdlet gets the previous versions of a configuration item.



Configuration Manager updates configuration items based on configuration management, software updates management, and operating system deployment. Configuration Manager stores the previous version of the item. The server removes previous versions, by default, when the data is more than 90 days old.



This cmdlet gets the history of an item for a specified item name. This cmdlet also gets the history for a specified revision of an item.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Introduction to Compliance Settings in Configuration Manager](Introduction to Compliance Settings in Configuration Manager)



* [Get-CMConfigurationItem](Get-CMConfigurationItem)



* [Get-CMConfigurationItemXMLDefinition](Get-CMConfigurationItemXMLDefinition)



* [New-CMConfigurationItem](New-CMConfigurationItem)



* [Set-CMConfigurationItem](Set-CMConfigurationItem)



* [Remove-CMConfigurationItem](Remove-CMConfigurationItem)



* [Import-CMConfigurationItem](Import-CMConfigurationItem)



* [Export-CMConfigurationItem](Export-CMConfigurationItem)



* [ConvertTo-CMConfigurationItem](ConvertTo-CMConfigurationItem)



* [ConvertFrom-CMConfigurationItem](ConvertFrom-CMConfigurationItem)





---


### Examples
#### Example 1: Get item history by name
```PowerShell
PS XYZ:\> Get-CMConfigurationItemHistory -Name "CMCI07"
```
This command gets the history for a configuration item named CMCI07.
#### Example 2: Get item history by ID
```PowerShell
PS XYZ:\> Get-CMConfigurationItemHistory -Id "16777568"
```
This command gets the previous version of a configuration item with the specified ID.


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

Specifies an ID for a configuration item revision.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a configuration item object. To obtain a configuration item object, use the Get-CMConfigurationItem (Get-CMConfigurationItem.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies an array of names of configuration items.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **Revision**

Specifies the version of a configuration item as an integer.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_ConfigurationItem


* IResultObject#SMS_ConfigurationItem






---


### Notes




---


### Syntax
```PowerShell
Get-CMConfigurationItemHistory [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Revision <Int32>] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationItemHistory [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Revision <Int32>] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationItemHistory [-Name] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Revision <Int32>] [<CommonParameters>]
```
