New-CMThirdPartyUpdateCatalog
-----------------------------




### Synopsis
Create a new third-party software updates catalog.



---


### Description

Use this cmdlet to create a new third-party updates catalog. For more information, see Enable third-party software updates (/mem/configmgr/sum/deploy-use/third-party-software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMThirdPartyUpdateCatalog](Get-CMThirdPartyUpdateCatalog)



* [Remove-CMThirdPartyUpdateCatalog](Remove-CMThirdPartyUpdateCatalog)



* [Set-CMThirdPartyUpdateCatalog](Set-CMThirdPartyUpdateCatalog)



* [Publish-CMThirdPartySoftwareUpdateContent](Publish-CMThirdPartySoftwareUpdateContent)



* [Get-CMThirdPartyUpdateCategory](Get-CMThirdPartyUpdateCategory)



* [Set-CMThirdPartyUpdateCategory](Set-CMThirdPartyUpdateCategory)



* [Enable third-party software updates](Enable third-party software updates)





---


### Examples
#### Example 1: Create a third-party update catalog
```PowerShell
New-CMThirdPartyUpdateCatalog -DownloadUrl $downloadUrl -PublisherName $publisher -Name $name -Description $description -SupportUrl $supportUrl -SupportContact $supportContact
```



---


### Parameters
#### **Description**

Specify a description for the third-party update catalog. The maximum length is 200 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |3       |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DownloadUrl**

Specify a valid HTTPS URL for the site to download the third-party update catalog.






|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[Uri]`|true    |0       |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specify a name for the third-party update catalog. The maximum length is 200 characters.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |2       |False        |CatalogName|



#### **PublisherName**

Specify the publisher name of the third-party update catalog. The maximum length is 200 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |False        |



#### **SupportContact**

Specify the support contact for the third-party update catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |5       |False        |



#### **SupportUrl**

Specify the support URL for the third-party update catalog.






|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[Uri]`|false   |4       |False        |





---


### Inputs
None





---


### Outputs
* IResultObject#SMS_ISVCatalogs






---


### Notes
This cmdlet returns the SMS_ISVCatalogs WMI class object.



---


### Syntax
```PowerShell
New-CMThirdPartyUpdateCatalog [-DownloadUrl] <Uri> [-PublisherName] <String> [-Name] <String> [-Description] <String> [[-SupportUrl] <Uri>] [[-SupportContact] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
