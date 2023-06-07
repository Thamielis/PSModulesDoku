New-CMGlobalConditionExpression
-------------------------------




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
#### **Description**

{{ Fill Description Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeviceType**

{{ Fill DeviceType Description }}



Valid Values:

* Windows
* WindowsMobile






|Type                         |Required|Position|PipelineInput|
|-----------------------------|--------|--------|-------------|
|`[GlobalConditionDeviceType]`|true    |named   |False        |



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

{{ Fill Name Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RootExpression**

{{ Fill RootExpression Description }}






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[ExpressionBase]`|true    |named   |False        |





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
New-CMGlobalConditionExpression [-Description <String>] -DeviceType {Windows | WindowsMobile} [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -RootExpression <ExpressionBase> [<CommonParameters>]
```
