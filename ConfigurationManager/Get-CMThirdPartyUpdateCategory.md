Get-CMThirdPartyUpdateCategory
------------------------------




### Synopsis
Get third-party software update categories.



---


### Description

Use this cmdlet to get third-party software update categories. For more information, see Enable third-party updates (/mem/configmgr/sum/deploy-use/third-party-software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMThirdPartyUpdateCategory](Set-CMThirdPartyUpdateCategory)



* [Get-CMThirdPartyUpdateCatalog](Get-CMThirdPartyUpdateCatalog)



* [New-CMThirdPartyUpdateCatalog](New-CMThirdPartyUpdateCatalog)



* [Remove-CMThirdPartyUpdateCatalog](Remove-CMThirdPartyUpdateCatalog)



* [Set-CMThirdPartyUpdateCatalog](Set-CMThirdPartyUpdateCatalog)



* [Publish-CMThirdPartySoftwareUpdateContent](Publish-CMThirdPartySoftwareUpdateContent)



* [Enable third-party software updates](Enable third-party software updates)





---


### Examples
#### Example 1: Get the category for a catalog object
```PowerShell
Get-CMThirdPartyUpdateCategory -Catalog $catalog
```

#### Example 2: Get the category for a catalog and category name
```PowerShell
Get-CMThirdPartyUpdateCategory -CatalogName $catalogName -Name $categoryName
```



---


### Parameters
#### **CatalogId**

Specify the ID of the third-party update catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **CatalogName**

Specify the name of the third-party update catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |0       |False        |



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

Specify the ID of the category.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |CategoryId|



#### **InputObject**

Specify an object for a third-party update catalog. To get this object, use the Get-CMThirdPartyUpdateCatalog (Get-CMThirdPartyUpdateCatalog.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Catalog|



#### **Name**

Specify the name of the category.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |CategoryName|



#### **ParentId**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PublishOption**





Valid Values:

* Skip
* MetadataOnly
* FullContent






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[PublishOptionType]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_ISVCatalogCategories


* IResultObject#SMS_ISVCatalogCategories






---


### Notes
This cmdlet returns an object of the SMS_ISVCatalogCategories WMI class.



---


### Syntax
```PowerShell
Get-CMThirdPartyUpdateCategory [-CatalogId] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [-Name <String>] [-ParentId <String>] [-PublishOption {Skip | MetadataOnly | FullContent}] [<CommonParameters>]
```
```PowerShell
Get-CMThirdPartyUpdateCategory [[-CatalogName] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [-Name <String>] [-ParentId <String>] [-PublishOption {Skip | MetadataOnly | FullContent}] [<CommonParameters>]
```
```PowerShell
Get-CMThirdPartyUpdateCategory [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] -InputObject <IResultObject> [-Name <String>] [-ParentId <String>] [-PublishOption {Skip | MetadataOnly | FullContent}] [<CommonParameters>]
```
