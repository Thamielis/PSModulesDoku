ConvertTo-CMConfigurationItem
-----------------------------




### Synopsis
Convert a Configuration Manager management iResultObject to a configuration item object.



---


### Description

The ConvertTo-CMConfigurationItem cmdlet converts a string which contains Configuration Item digest XML definition into a ConfigurationItem object.



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



* [ConvertFrom-CMConfigurationItem](ConvertFrom-CMConfigurationItem)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> $myCI = ConvertTo-CMConfigurationItem -DigestText $digestString
PS XYZ:\> $myCI.Persist($myCI)
```
This command converts a digest into a ConfigurationItem object, and then save the object to the site.


---


### Parameters
#### **DigestText**

Specifies the Digest text.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Specifies a configuration item object. To obtain a configuration item object, you can use the Get-CMConfigurationItem (Get-CMConfigurationItem.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|





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
ConvertTo-CMConfigurationItem -DigestText <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
ConvertTo-CMConfigurationItem [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
