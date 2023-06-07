Set-CMAssetIntelligenceCatalogItem
----------------------------------




### Synopsis
Changes the properties of an item in the Asset Intelligence catalog.



---


### Description

The Set-CMAssetIntelligenceCatalogItem cmdlet changes the properties of software categories, software families, and custom software labels in the Configuration Manager Asset Intelligence catalog.



The Asset Intelligence catalog contains categorization and identification information for software titles. The catalog includes predefined categories and families. Predefined items cannot be modified. In addition to predefined software categories and software families, you can create custom categories and families. You can also create custom software labels.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAssetIntelligenceCatalogItem](Get-CMAssetIntelligenceCatalogItem)



* [New-CMAssetIntelligenceCatalogItem](New-CMAssetIntelligenceCatalogItem)



* [Remove-CMAssetIntelligenceCatalogItem](Remove-CMAssetIntelligenceCatalogItem)





---


### Examples
#### Example 1: Change the properties of a catalog item by ID
```PowerShell
PS XYZ:\> Set-CMAssetIntelligenceCatalogItem -Id "1211" -NewCategoryName "Windows Databases" -Description "Windows-based databases" -LanguageId 1033
```
This command changes the category name, description, and language ID for the Asset Intelligence catalog item that has the category ID 1211.
#### Example 2: Change the properties of a catalog item category of items
```PowerShell
PS XYZ:\> Set-CMAssetIntelligenceCatalogItem -CategoryName "Database Tools" -NewCategoryName "Database Clients" -Description "Database client software" -LanguageId 1033
```
This command changes the category name, description, and language ID for the Asset Intelligence catalog item that has the category name Database Tools.
#### Example 3: Rename a category
```PowerShell
PS XYZ:\> Set-CMAssetIntelligenceCatalogItem -CategoryName "Database Clients" -NewCategoryName "Database Server Tools"
```
This command changes the category name of the Asset Intelligence catalog item that has the category name Database Clients to Database Server Tools.


---


### Parameters
#### **CategoryName**

Specifies the name of a category, family, or label in the Asset Intelligence catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Description**

Specifies the description of a category, family, or label in the Asset Intelligence catalog.






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



#### **InputObject**

Specifies an Asset Intelligence catalog item. To get an Asset Intelligence catalog item, use the Get-CMAssetIntelligenceCatalogItem cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **LanguageId**

Specifies the locale ID for an item. For more information and a list of locale IDs, see Appendix A: Product Behavior (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **NewCategoryName**

Specifies a new category name for a category, family, or label in the Asset Intelligence catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Set-CMAssetIntelligenceCatalogItem -CategoryName <String> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-LanguageId <Int32>] [-NewCategoryName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAssetIntelligenceCatalogItem [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-LanguageId <Int32>] [-NewCategoryName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAssetIntelligenceCatalogItem [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-LanguageId <Int32>] [-NewCategoryName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
