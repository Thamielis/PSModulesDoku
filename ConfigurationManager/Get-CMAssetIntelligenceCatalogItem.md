Get-CMAssetIntelligenceCatalogItem
----------------------------------




### Synopsis
Gets an item from the Asset Intelligence catalog.



---


### Description

The Get-CMAssetIntelligenceCatalogItem cmdlet gets software categories, software families, and custom software labels from the Asset Intelligence catalog in Configuration Manager.



The Asset Intelligence catalog contains categorization and identification information for software titles. The catalog includes predefined categories and families. Predefined items cannot be modified. In addition to predefined software categories and software families, you can create custom categories and families. You can also create custom software labels.



For more information about the Asset Intelligence catalog, see Introduction to Asset Intelligence in Configuration Manager (/mem/configmgr/core/clients/manage/asset-intelligence/configuring-asset-intelligence).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAssetIntelligenceCatalogItem](New-CMAssetIntelligenceCatalogItem)



* [Remove-CMAssetIntelligenceCatalogItem](Remove-CMAssetIntelligenceCatalogItem)



* [Set-CMAssetIntelligenceCatalogItem](Set-CMAssetIntelligenceCatalogItem)





---


### Examples
#### Example 1: Get catalog items by category name
```PowerShell
PS XYZ:\> Get-CMAssetIntelligenceCatalogItem -CategoryName "Browsers"
```
This command gets Asset Intelligence catalog items by category name.
#### Example 2: Get catalog items by category ID
```PowerShell
PS XYZ:\> Get-CMAssetIntelligenceCatalogItem -Id "1211"
```
This command gets Asset Intelligence catalog items by category ID.


---


### Parameters
#### **CategoryName**

Specifies the name of a category, family, or label in the Asset Intelligence catalog.






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

Specifies an array of IDs of asset intelligence catalog items.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |CategoryId|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_AICategory


* IResultObject#SMS_AICategory






---


### Notes




---


### Syntax
```PowerShell
Get-CMAssetIntelligenceCatalogItem [-CategoryName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMAssetIntelligenceCatalogItem [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
