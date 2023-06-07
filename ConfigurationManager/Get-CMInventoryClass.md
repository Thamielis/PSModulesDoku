Get-CMInventoryClass
--------------------




### Synopsis
{{ Fill in the Synopsis }}



---


### Description

{{ Fill in the Description }}



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> {{ Add example code here }}
```
{{ Add example description here }}


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



#### **GroupName**

{{ Fill GroupName Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Id**

{{ Fill Id Description }}






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |SMSClassID|



#### **Name**

{{ Fill Name Description }}






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|false   |named   |False        |ClassName|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_InventoryClass


* IResultObject#SMS_InventoryClass






---


### Notes




---


### Syntax
```PowerShell
Get-CMInventoryClass [-DisableWildcardHandling] [-ForceWildcardHandling] [-GroupName <String>] [-Id <String>] [-Name <String>] [<CommonParameters>]
```
