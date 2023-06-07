Set-CMThirdPartyUpdateCategory
------------------------------




### Synopsis
Modify third-party software update categories.



---


### Description

Use this cmdlet to modify third-party software update categories. For more information, see Enable third-party updates (/mem/configmgr/sum/deploy-use/third-party-software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMThirdPartyUpdateCategory](Get-CMThirdPartyUpdateCategory)



* [Get-CMThirdPartyUpdateCatalog](Get-CMThirdPartyUpdateCatalog)



* [New-CMThirdPartyUpdateCatalog](New-CMThirdPartyUpdateCatalog)



* [Remove-CMThirdPartyUpdateCatalog](Remove-CMThirdPartyUpdateCatalog)



* [Set-CMThirdPartyUpdateCatalog](Set-CMThirdPartyUpdateCatalog)



* [Publish-CMThirdPartySoftwareUpdateContent](Publish-CMThirdPartySoftwareUpdateContent)



* [Enable third-party software updates](Enable third-party software updates)





---


### Examples
#### Example 1
```PowerShell
Set-CMThirdPartyUpdateCategory -Catalog $catalog -Id $categoryId -PublishOption $publishOption -EnableCategories $true
$catalog | Set-CMThirdPartyUpdateCategory -Name $categoryName -PublishOption $publishOption -EnableCategories $true
Set-CMThirdPartyUpdateCategory -CatalogId $catalogId -ParentId $parentId -PublishOption $publishOption -EnableCategories $true
Set-CMThirdPartyUpdateCategory -CatalogName $catalogName -Name $categoryName -ParentId $parentId -PublishOption $publishOption -EnableCategories $true
Set-CMThirdPartyUpdateCategory -Categories $categories -PublishOption $publishOption -EnableCategories $true
```



---


### Parameters
#### **CatalogId**

Specify the ID of the third-party update catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |0       |False        |



#### **CatalogName**

Specify the name of the third-party update catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |0       |False        |



#### **Category**

Specify an object for the the third-party update catalog category.






|Type               |Required|Position|PipelineInput|Aliases   |
|-------------------|--------|--------|-------------|----------|
|`[IResultObject[]]`|true    |0       |False        |Categories|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableCategory**

Enable the catagory for the third-party update catalog.






|Type       |Required|Position|PipelineInput|Aliases         |
|-----------|--------|--------|-------------|----------------|
|`[Boolean]`|false   |named   |False        |EnableCategories|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the category ID for the third-party update catalog.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |CategoryId|



#### **InputObject**

Specify an object for the third-party update catalog. To get this object, use the Get-CMThirdPartyUpdateCatalog (Get-CMThirdPartyUpdateCatalog.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Catalog|



#### **Name**

Specify the category name for the third-party update catalog.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |CategoryName|



#### **ParentId**

Specify the parent ID of the the third-party update catalog category.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PublishOption**





Valid Values:

* Skip
* MetadataOnly
* FullContent






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[PublishOptionType]`|false   |named   |False        |



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
* IResultObject#SMS_ISVCatalogCategories






---


### Notes
This cmdlet returns an object of the SMS_ISVCatalogCategories WMI class.



---


### Syntax
```PowerShell
Set-CMThirdPartyUpdateCategory [[-CatalogId] <String>] [-DisableWildcardHandling] [-EnableCategory <Boolean>] [-ForceWildcardHandling] [-Id <String>] [-Name <String>] [-ParentId <String>] [-PassThru] [-PublishOption {Skip | MetadataOnly | FullContent}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMThirdPartyUpdateCategory [[-CatalogName] <String>] [-DisableWildcardHandling] [-EnableCategory <Boolean>] [-ForceWildcardHandling] [-Id <String>] [-Name <String>] [-ParentId <String>] [-PassThru] [-PublishOption {Skip | MetadataOnly | FullContent}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMThirdPartyUpdateCategory [-Category] <IResultObject[]> [-DisableWildcardHandling] [-EnableCategory <Boolean>] [-ForceWildcardHandling] [-PassThru] [-PublishOption {Skip | MetadataOnly | FullContent}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMThirdPartyUpdateCategory [-DisableWildcardHandling] [-EnableCategory <Boolean>] [-ForceWildcardHandling] [-Id <String>] -InputObject <IResultObject> [-Name <String>] [-ParentId <String>] [-PassThru] [-PublishOption {Skip | MetadataOnly | FullContent}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
