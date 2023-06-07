Add-CMComplianceSettingDirectory
--------------------------------




### Synopsis
Adds a compliance setting directory



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



---


### Parameters
#### **Description**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DirectoryName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Existence**





Valid Values:

* MustExist
* MustNotExist
* Occurs






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[ExistenceType]`|true    |named   |False        |



#### **ExistentialRule**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ExpectedValue**








|Type        |Required|Position|PipelineInput|Aliases                                            |
|------------|--------|--------|-------------|---------------------------------------------------|
|`[String[]]`|false   |named   |False        |ExpectedValues<br/>ExpectedCount<br/>ExpectedCounts|



#### **ExpressionOperator**





Valid Values:

* And
* Or
* Other
* IsEquals
* NotEquals
* GreaterThan
* LessThan
* Between
* NotBetween
* GreaterEquals
* LessEquals
* BeginsWith
* NotBeginsWith
* EndsWith
* NotEndsWith
* Contains
* NotContains
* AllOf
* OneOf
* NoneOf
* SetEquals
* SubsetOf
* ExcludesAll






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[RuleExpressionOperator]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IncludeSubfolders**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[PSObject]`|true    |named   |True (ByValue)|



#### **Is64Bit**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |SettingName|



#### **NoncomplianceSeverity**





Valid Values:

* None
* Informational
* Warning
* Critical
* CriticalWithEvent






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[NoncomplianceSeverity]`|false   |named   |False        |



#### **NoRule**








|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[Switch]`|false   |named   |False        |NoRules|



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RuleDescription**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RuleName**








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
System.Management.Automation.PSObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Add-CMComplianceSettingDirectory [-Description <String>] -DirectoryName <String> [-DisableWildcardHandling] -Existence {MustExist | MustNotExist | Occurs} -ExistentialRule [-ExpectedValue <String[]>] [-ExpressionOperator {IsEquals | NotEquals | GreaterThan | GreaterEquals | LessThan | LessEquals | Between | OneOf | NoneOf}] [-ForceWildcardHandling] [-IncludeSubfolders] -InputObject <PSObject> [-Is64Bit] -Name <String> [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] [-PassThru] -Path <String> [-RuleDescription <String>] [-RuleName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMComplianceSettingDirectory [-Description <String>] -DirectoryName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IncludeSubfolders] -InputObject <PSObject> [-Is64Bit] -Name <String> [-NoRule] [-PassThru] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
