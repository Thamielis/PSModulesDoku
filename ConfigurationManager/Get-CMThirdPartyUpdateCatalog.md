Get-CMThirdPartyUpdateCatalog
-----------------------------




### Synopsis
Get a third-party updates catalog.



---


### Description

Use this cmdlet to get a third-party updates catalog. For more information, see Enable third-party software updates (/mem/configmgr/sum/deploy-use/third-party-software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMThirdPartyUpdateCatalog](New-CMThirdPartyUpdateCatalog)



* [Remove-CMThirdPartyUpdateCatalog](Remove-CMThirdPartyUpdateCatalog)



* [Set-CMThirdPartyUpdateCatalog](Set-CMThirdPartyUpdateCatalog)



* [Publish-CMThirdPartySoftwareUpdateContent](Publish-CMThirdPartySoftwareUpdateContent)



* [Get-CMThirdPartyUpdateCategory](Get-CMThirdPartyUpdateCategory)



* [Set-CMThirdPartyUpdateCategory](Set-CMThirdPartyUpdateCategory)



* [Enable third-party software updates](Enable third-party software updates)





---


### Examples
#### Example 1: Get a catalog by ID
```PowerShell
Get-CMThirdPartyUpdateCatalog -Id $id
```

#### Example 2: Get a catalog by name
```PowerShell
Get-CMThirdPartyUpdateCatalog -Name $name
```

#### Example 3: Get all catalogs for a site
```PowerShell
Get-CMThirdPartyUpdateCatalog -SiteCode $siteCode
```

#### Example 4: Get all custom catalogs
```PowerShell
Get-CMThirdPartyUpdateCatalog -IsCustomCatalog $true
```



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

Specify the ID of the catalog. The format is a standard GUID.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |0       |False        |CatalogId|



#### **IsCustomCatalog**

To filter the results for only custom catalogs, set this parameter to `$true`.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsSyncEnabled**

To filter the results for only catalogs that you enable for sync, set this parameter to `$true`.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify the name of the catalog.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |0       |False        |CatalogName|



#### **PublisherName**

Specify the name of the catalog's publisher.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteCode**

Specify the site code to filter the results for a specific site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_ISVCatalogs


* IResultObject#SMS_ISVCatalogs






---


### Notes
This cmdlet returns the SMS_ISVCatalogs WMI class object.



---


### Syntax
```PowerShell
Get-CMThirdPartyUpdateCatalog [-Id] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsCustomCatalog <Boolean>] [-IsSyncEnabled <Boolean>] [-PublisherName <String>] [-SiteCode <String>] [<CommonParameters>]
```
```PowerShell
Get-CMThirdPartyUpdateCatalog [[-Name] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsCustomCatalog <Boolean>] [-IsSyncEnabled <Boolean>] [-PublisherName <String>] [-SiteCode <String>] [<CommonParameters>]
```
