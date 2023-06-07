Get-CMSoftwareUpdateCategory
----------------------------




### Synopsis
Get a software update classification or product.



---


### Description

Use this cmdlet to get an object for a software update classification or product. Software updates metadata is retrieved during the synchronization process in Configuration Manager based on the settings that you specify in the software update point component properties. For more information, see Configure classifications and products to synchronize (/mem/configmgr/sum/get-started/configure-classifications-and-products).



To filter the results that this cmdlet returns, use the CategoryTypeName and IsSubscribed properties. The category types include UpdateClassification , Company , ProductFamily , and Product . When the IsSubscribed property is True , the site is configured to synchronize that category.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate)





---


### Examples
#### Example 1: Show subscribed classifications
```PowerShell
Get-CMSoftwareUpdateCategory -Fast -TypeName "UpdateClassification" | Where-Object { $_.IsSubscribed } | Select-Object LocalizedCategoryInstanceName
```
To change this command to return the list of classifications that the site isn't synchronizing, add the not operator (`!`) before the reference to the IsSubscribed property. For example, `!$_.IsSubscribed`
#### Example 2: Count categories by type
```PowerShell
Get-CMSoftwareUpdateCategory -Fast | Group-Object -Property CategoryTypeName

Count Name
----- ----
   13 UpdateClassification
    7 Company
   59 ProductFamily
  338 Product
```

#### Example 3: Show products for Office product family
```PowerShell
$officeFamily = Get-CMSoftwareUpdateCategory -Fast -TypeName "ProductFamily" | Where-Object { $_.LocalizedCategoryInstanceName -eq "Office" }

Get-CMSoftwareUpdateCategory -Fast | Where-Object ParentCategoryInstanceId -eq $officeFamily.CategoryInstanceID | Select-Object LocalizedCategoryInstanceName,CategoryTypeName

LocalizedCategoryInstanceName         CategoryTypeName
-----------------------------         ----------------
Dictionary Updates for Microsoft IMEs Product
New Dictionaries for Microsoft IMEs   Product
Office 2002/XP                        Product
Office 2003                           Product
Office 2007                           Product
Office 2010                           Product
Office 2013                           Product
Office 2016                           Product
Office 365 Client                     Product
Office 2019                           Product
```

#### Example 4: Get all software updates in Office 365 Client category
```PowerShell
$cat = Get-CMSoftwareUpdateCategory -Fast -TypeName "Product" | Where-Object { $_.LocalizedCategoryInstanceName -eq "Office 365 Client" }

Get-CMSoftwareUpdate -Fast -Category $cat | Select-Object ArticleID,LocalizedDisplayName,IsDeployed,IsSuperseded,NumTotal,NumMissing
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the category to get.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |CategoryInstanceID|



#### **Name**

Specify the name of the category to get.






|Type      |Required|Position|PipelineInput|Aliases                                       |
|----------|--------|--------|-------------|----------------------------------------------|
|`[String]`|false   |named   |False        |LocalizedCategoryInstanceName<br/>CategoryName|



#### **TypeName**

Specify the type of category to get. Common values include the following types:


* UpdateClassification


* Company


* ProductFamily


* Product






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|false   |named   |False        |CategoryTypeName|



#### **UniqueId**

Specify the unique ID for the category to get. This value is the type name with a GUID for the category. For example, `UpdateClassification:77835c8d-62a7-41f5-82ad-f28d1af1e3b1`






|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|true    |named   |False        |CategoryInstance_UniqueID|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_UpdateCategoryInstance


* IResultObject#SMS_UpdateCategoryInstance






---


### Notes
For more information on this return object and its properties, see SMS_UpdateCategoryInstance server WMI class (/mem/configmgr/develop/reference/sum/sms_updatecategoryinstance-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMSoftwareUpdateCategory [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdateCategory [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [-TypeName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdateCategory [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -UniqueId <String> [<CommonParameters>]
```
