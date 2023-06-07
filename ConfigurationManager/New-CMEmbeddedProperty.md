New-CMEmbeddedProperty
----------------------




### Synopsis
Creates an embedded property.



---


### Description

The New-CMEmbeddedProperty cmdlet creates an embedded property.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMEmbeddedObjectInstance](New-CMEmbeddedObjectInstance)



* [New-CMEmbeddedPropertyList](New-CMEmbeddedPropertyList)





---


### Examples
#### Example 1: Create an embedded property
```PowerShell
PS ABC:\> New-CMEmbeddedProperty -PropertyName "UserName" -Value 0 -Value1 1 -Value2 Administrator
```
This command creates an embedded property named UserName with the value of 0, the value1 of 1, and the value2 of Administrator.


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



#### **PropertyName**

Specifies a name for the property.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **Value**

Specifies a value for the property.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Value1**

Specifies a value for the property.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Value2**

Specifies a value for the property.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMEmbeddedProperty [-DisableWildcardHandling] [-ForceWildcardHandling] -PropertyName <String> [-Value <Int32>] [-Value1 <String>] [-Value2 <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
