New-CMCategory
--------------




### Synopsis
Creates a configuration category in Configuration Manager.



---


### Description

The New-CMCategory cmdlet creates a configuration category in Configuration Manager. Configuration categories offer an optional method of sorting and filtering configuration baselines and configuration items in Configuration Manager and Configuration Manager reports.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMCategory](Remove-CMCategory)



* [Get-CMCategory](Get-CMCategory)





---


### Examples
#### Example 1: Create a configuration category
```PowerShell
PS XYZ:\> New-CMCategory -CategoryType "DriverCategories" -Name "NewLaptopDriverSet"
```
This command creates a new category in DriverCategories named NewLaptopDriverSet.


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
|`[CategoryType]`|true    |named   |False        |



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



#### **Name**

Specifies a name for the configuration category.






|Type      |Required|Position|PipelineInput|Aliases                      |
|----------|--------|--------|-------------|-----------------------------|
|`[String]`|true    |named   |False        |LocalizedCategoryInstanceName|



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
* IResultObject#SMS_CategoryInstance






---


### Notes




---


### Syntax
```PowerShell
New-CMCategory -CategoryType {AppCategories | BaselineCategories | CatalogCategories | DriverCategories | UserCategories} [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
