Rename-CMCategory
-----------------




### Synopsis
Renames a category.



---


### Description

The Rename-CMCategory cmdlet renames a category instance.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMCategory](New-CMCategory)



* [Get-CMCategory](Get-CMCategory)



* [Remove-CMCategory](Remove-CMCategory)





---


### Examples
#### Example 1: Rename a category by getting a category object
```PowerShell
PS ABC:\> $Category = Get-CMCategory -Name "Category01" -CategoryType BaselineCategories
PS ABC:\> Rename-CMCategory -InputObject $Category -NewName "NewCategory01"
```
The first command gets the category object named Category01 of the type BaselineCategories and stores the object in the $Category variable.


The second command renames the category stored in $Category to NewCategory01.
#### Example 2: Rename a category by its name and type
```PowerShell
PS ABC:\> Rename-CMCategory -Name "Category02" -NewName "NewCategory02" -CategoryType BaselineCategories
```
This command renames the category named Category02 of the type BaseineCategories to NewCategory02.
#### Example 3: Rename a category by passing a category object through the pipeline
```PowerShell
PS ABC:\> Get-CMCategory -Name "Category03" -CategoryType BaselineCategories | Rename-CMCategory -NewName "NewCategory03"
```
This command gets the category object named Category03 of the type BaselineCategories and uses the pipeline operator to pass the object to Rename-CMCategory , which renames the category to NewCategory03.


---


### Parameters
#### **CategoryType**

Specifies a category type. Valid values are:


* AppCategories


* BaselineCategories


* CatalogCategories


* DriverCategories


* UserCategories



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



#### **InputObject**

Specifies a category instance object. To obtain a category instance object, use the Get-CMCategory (Get-CMCategory.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases |
|-----------------|--------|--------|--------------|--------|
|`[IResultObject]`|true    |named   |True (ByValue)|Category|



#### **Name**

Specifies the name of a category instance.






|Type      |Required|Position|PipelineInput|Aliases                                       |
|----------|--------|--------|-------------|----------------------------------------------|
|`[String]`|true    |named   |False        |LocalizedCategoryInstanceName<br/>CategoryName|



#### **NewName**

Specifies a new name for the category instance.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Rename-CMCategory -CategoryType {AppCategories | BaselineCategories | CatalogCategories | DriverCategories | UserCategories} [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -NewName <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Rename-CMCategory [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -NewName <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
