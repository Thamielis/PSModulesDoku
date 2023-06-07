Remove-CMAssetIntelligenceCatalogItem
-------------------------------------




### Synopsis
Removes an item from the Asset Intelligence catalog.



---


### Description

The Remove-CMAssetIntelligenceCatalogItem cmdlet removes software categories, software families, and custom software labels from the Asset Intelligence catalog in Configuration Manager.



The Asset Intelligence catalog contains categorization and identification information for software titles. The catalog includes predefined categories and families. Predefined items cannot be modified. In addition to predefined software categories and software families, you can create custom categories and families. You can also create custom software labels.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAssetIntelligenceCatalogItem](Get-CMAssetIntelligenceCatalogItem)



* [New-CMAssetIntelligenceCatalogItem](New-CMAssetIntelligenceCatalogItem)



* [Set-CMAssetIntelligenceCatalogItem](Set-CMAssetIntelligenceCatalogItem)





---


### Examples
#### Example 1: Remove a catalog item by category name
```PowerShell
PS XYZ:\> Remove-CMAssetIntelligenceCatalogItem -CategoryName "Database Tools"
```
This command removes the category named Database Tools from the Asset Intelligence catalog.


---


### Parameters
#### **CategoryName**

Specifies the name of a category, family, or label in the Asset Intelligence catalog.






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
Remove-CMAssetIntelligenceCatalogItem -CategoryName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAssetIntelligenceCatalogItem [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAssetIntelligenceCatalogItem [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
