Get-CMDeviceCategory
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



#### **Id**

{{ Fill Id Description }}






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |CategoryId|



#### **Name**

{{ Fill Name Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_MDMDeviceCategory


* IResultObject#SMS_MDMDeviceCategory






---


### Notes




---


### Syntax
```PowerShell
Get-CMDeviceCategory [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCategory [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
