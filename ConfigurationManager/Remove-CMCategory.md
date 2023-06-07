Remove-CMCategory
-----------------




### Synopsis
Removes a configuration category in Configuration Manager.



---


### Description

The Remove-CMCategory cmdlet removes a configuration category in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCategory](Get-CMCategory)



* [New-CMCategory](New-CMCategory)





---


### Examples
#### Example 1: Remove a configuration category
```PowerShell
PS XYZ:\> Remove-CMCategory -CategoryType "DriverCategories" -Force -Name "NewLaptopDriverSet"
```
This command removes the category named NewLaptopDriverSet from DriversCategories without prompting you for confirmation.


---


### Parameters
#### **CategoryType**

Specifies a category type. Valid values are:


* UserCategories


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

Specifies an array of IDs of configuration categories.






|Type        |Required|Position|PipelineInput|Aliases                                |
|------------|--------|--------|-------------|---------------------------------------|
|`[String[]]`|true    |named   |False        |CategoryInstanceUniqueid<br/>CategoryId|



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases |
|-----------------|--------|--------|--------------|--------|
|`[IResultObject]`|true    |named   |True (ByValue)|Category|



#### **Name**

Specifies an array of names of configuration categories.






|Type        |Required|Position|PipelineInput|Aliases                                       |
|------------|--------|--------|-------------|----------------------------------------------|
|`[String[]]`|true    |named   |False        |LocalizedCategoryInstanceName<br/>CategoryName|



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
Remove-CMCategory -CategoryType {UserCategories | BaselineCategories | DriverCategories | AppCategories | GlobalCondition | CatalogCategories | UserCategories | BaselineCategories | DriverCategories | AppCategories | GlobalCondition | CatalogCategories} [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCategory [-CategoryType {UserCategories | BaselineCategories | DriverCategories | AppCategories | GlobalCondition | CatalogCategories | UserCategories | BaselineCategories | DriverCategories | AppCategories | GlobalCondition | CatalogCategories}] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCategory [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCategory [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
