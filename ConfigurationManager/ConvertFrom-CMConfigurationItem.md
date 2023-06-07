ConvertFrom-CMConfigurationItem
-------------------------------




### Synopsis
Converts a Configuration Manager configuration item to a string.



---


### Description

The ConvertFrom-CMConfigurationItem cmdlet converts a ConfigurationItem object into a string which contains the XML definition of the ConfigurationItem object.



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



* [Export-CMConfigurationItem](Export-CMConfigurationItem)



* [ConvertTo-CMConfigurationItem](ConvertTo-CMConfigurationItem)





---


### Parameters
#### **ConfigurationItem**

Specifies a configuration item.






|Type                 |Required|Position|PipelineInput |
|---------------------|--------|--------|--------------|
|`[ConfigurationItem]`|true    |0       |True (ByValue)|



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





---


### Inputs
Microsoft.ConfigurationManagement.DesiredConfigurationManagement.ConfigurationItem





---


### Outputs
* [String](https://learn.microsoft.com/en-us/dotnet/api/System.String)






---


### Notes




---


### Syntax
```PowerShell
ConvertFrom-CMConfigurationItem [-ConfigurationItem] <ConfigurationItem> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
