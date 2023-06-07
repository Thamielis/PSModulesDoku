New-CMAssetIntelligenceCatalogItem
----------------------------------




### Synopsis
Creates an item for the Asset Intelligence catalog.



---


### Description

The New-CMAssetIntelligenceCatalogItem cmdlet creates software categories, software families, and custom software labels from the Asset Intelligence catalog in Configuration Manager.



The Asset Intelligence catalog contains categorization and identification information for software titles. The catalog includes predefined categories and families. Predefined items cannot be modified. In addition to predefined software categories and software families, you can create custom categories and families. You can also create custom software labels.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAssetIntelligenceCatalogItem](Get-CMAssetIntelligenceCatalogItem)



* [Remove-CMAssetIntelligenceCatalogItem](Remove-CMAssetIntelligenceCatalogItem)



* [Set-CMAssetIntelligenceCatalogItem](Set-CMAssetIntelligenceCatalogItem)





---


### Examples
#### Example 1: Create category label item in the catalog
```PowerShell
PS XYZ:\> New-CMAssetIntelligenceCatalogItem -CategoryName "Databases" -LanguageId 1033 -Type TypeTag
```
This command creates a category label in the Asset Intelligence catalog named Databases that has a language ID of 1033 and a type of TypeTag.
#### Example 2: Create a category item in the catalog
```PowerShell
PS XYZ:\> New-CMAssetIntelligenceCatalogItem -CategoryName "Database Tools" -Type TypeCategory
```
This command creates a category in the Asset Intelligence catalog named Database Tools that has a type of TypeCategory.
#### Example 3: Create a category family in the catalog
```PowerShell
PS XYZ:\> New-CMAssetIntelligenceCatalogItem -CategoryName "Database Software" -Type TypeFamily
```
This command creates a category family item in the Asset Intelligence catalog family named Database Software that has a type of TypeFamily.


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



#### **LanguageId**

Specifies the locale ID for an item. For more information and a list of locale IDs, see Appendix A: Product Behavior (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Type**

Specifies the type of Asset Intelligence catalog item. The acceptable values for this parameter are:


* TypeCategory


* TypeFamily


* TypeTag



Valid Values:

* TypeCategory
* TypeFamily
* TypeTag






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Types]`|true    |named   |False        |



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
None





---


### Outputs
* IResultObject#SMS_AICategory






---


### Notes




---


### Syntax
```PowerShell
New-CMAssetIntelligenceCatalogItem -CategoryName <String> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-LanguageId <Int32>] -Type {TypeCategory | TypeFamily | TypeTag} [-Confirm] [-WhatIf] [<CommonParameters>]
```
