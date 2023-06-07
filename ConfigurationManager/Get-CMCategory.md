Get-CMCategory
--------------




### Synopsis
Gets configuration categories in Configuration Manager.



---


### Description

The Get-CMCategory cmdlet gets configuration categories in Configuration Manager. Configuration categories offer an optional method of sorting and filtering configuration baselines and configuration items in Configuration Manager and Configuration Manager reports.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMCategory](New-CMCategory)



* [Remove-CMCategory](Remove-CMCategory)





---


### Examples
#### Example 1: Get configuration categories by using a name
```PowerShell
PS XYZ:\> Get-CMCategory -CategoryType "DriverCategories" -Name "NewLaptopDriverSet"
```
This command gets configuration driver categories in Configuration Manager that have the name NewLaptopDriverSet.


---


### Parameters
#### **CategoryType**

Specifies a category type. Valid values are:


* BaselineCategories


* DriverCategories


* AppCategories


* GlobalCondition


* CatalogCategories



Valid Values:

* UserCategories
* BaselineCategories
* DriverCategories
* AppCategories
* GlobalCondition
* CatalogCategories






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[CategoryType]`|false   |named   |False        |



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

Specifies an array of IDs of configuration categories.






|Type        |Required|Position|PipelineInput|Aliases                                |
|------------|--------|--------|-------------|---------------------------------------|
|`[String[]]`|true    |named   |False        |CategoryInstanceUniqueid<br/>CategoryId|



#### **Name**

Specifies an array of names of configuration categories.






|Type      |Required|Position|PipelineInput|Aliases                                       |
|----------|--------|--------|-------------|----------------------------------------------|
|`[String]`|false   |named   |False        |LocalizedCategoryInstanceName<br/>CategoryName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_CategoryInstance


* IResultObject#SMS_CategoryInstance






---


### Notes




---


### Syntax
```PowerShell
Get-CMCategory [-CategoryType {UserCategories | BaselineCategories | DriverCategories | AppCategories | GlobalCondition | CatalogCategories}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
```PowerShell
Get-CMCategory [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String[]> [<CommonParameters>]
```
