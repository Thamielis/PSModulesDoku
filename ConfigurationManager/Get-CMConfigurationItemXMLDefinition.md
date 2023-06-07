Get-CMConfigurationItemXMLDefinition
------------------------------------




### Synopsis
Gets an XML definition of a configuration item in Configuration Manager.



---


### Description

The Get-CMConfigurationItemXMLDefinition cmdlet gets an XML definition of a configuration item object as a string. You can specify a configuration item with the configuration item ID, the configuration item name, or using the Get-CMConfigurationItem (Get-CMConfigurationItem.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Introduction to Compliance Settings in Configuration Manager](Introduction to Compliance Settings in Configuration Manager)



* [Get-CMConfigurationItem](Get-CMConfigurationItem)



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
#### Example 1: Get XML formatted item using an ID
```PowerShell
PS XYZ:\> Get-CMConfigurationItemXMLDefinition -Id "16777568"
```
This command gets a configuration item formatted in XML for the item that has the specified identifier.
#### Example 2: Get XML formatted item using a name
```PowerShell
PS XYZ:\> Get-CMConfigurationItemXMLDefinition -Name "ConfigItem76"
```
This command gets a configuration item formatted in XML for the item named ConfigItem76.
#### Example 3: Get XML formatted item using a variable
```PowerShell
PS XYZ:\> $CIObj=Get-CMConfigurationItem -Id "16777568"
PS XYZ:\> Get-CMConfigurationItemXMLDefinition -InputObject $CIObj
```
The first command uses the Get-CMConfigurationItem (Get-CMConfigurationItem.md)cmdlet to get a configuration item with the specified ID, and then stores it in the $CIObj variable.


The second command gets a configuration item formatted in XML for the item stored in $CIObj.


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

Specifies an array of IDs of configuration items. You can use a comma-separated list.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a configuration item object. To get a configuration item object, use the Get-CMConfigurationItem (Get-CMConfigurationItem.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies an array of names of configuration items. You can use a comma-separated list.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |0       |False        |LocalizedDisplayName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [String](https://learn.microsoft.com/en-us/dotnet/api/System.String)


* [String[]](https://learn.microsoft.com/en-us/dotnet/api/System.String[])






---


### Notes




---


### Syntax
```PowerShell
Get-CMConfigurationItemXMLDefinition [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationItemXMLDefinition [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationItemXMLDefinition [[-Name] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
