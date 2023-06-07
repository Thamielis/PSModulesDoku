Get-CMInitialModifiableSecuredCategory
--------------------------------------




### Synopsis
Gets modifiable secured categories.



---


### Description

The Get-CMInitialModifiableSecuredCategory cmdlet gets modifiable secured categories from Configuration Manager.



Note: This cmdlet was previously known as Get-CMInitModifiableSecuredCategory in System Center 2012 Configuration Manager SP1.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Get information about all your modifiable secured categories
```PowerShell
PS XYZ:\> Get-CMInitialModifiableSecuredCategory
```
This command returns information about all your modifiable secured categories.
#### Example 2: Get information about a specific modifiable secured category
```PowerShell
PS XYZ:\> Get-CMInitialModifiableSecuredCategory -ID "121989"
```
This command returns information about the modifiable secured category that has the ID 121989.


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

Specifies an identifier in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |CategoryId|



#### **Name**

Specifies a name in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |CategoryName|



#### **ObjectTypeId**

Specifies an ID for an object type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_InitModifiableSecuredCategory


* IResultObject#SMS_InitModifiableSecuredCategory






---


### Notes




---


### Syntax
```PowerShell
Get-CMInitialModifiableSecuredCategory [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] [-ObjectTypeId <String>] [<CommonParameters>]
```
```PowerShell
Get-CMInitialModifiableSecuredCategory [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-ObjectTypeId <String>] [<CommonParameters>]
```
