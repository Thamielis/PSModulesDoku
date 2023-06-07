Add-CMComplianceSettingWqlQuery
-------------------------------




### Synopsis
Adds a compliance setting wql query



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
#### **ClassName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DataType**





Valid Values:

* String
* Integer
* DateTime
* FloatingPoint
* Version
* StringArray
* Boolean
* IntegerArray






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[SettingDataType]`|true    |named   |False        |



#### **Description**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
|`[String[]]`|true    |named   |False        |ExpectedValues<br/>ExpectedCount<br/>ExpectedCounts|



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
|`[RuleExpressionOperator]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[PSObject]`|true    |named   |True (ByValue)|



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |SettingName|



#### **Namespace**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **Property**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Remediate**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ReportNoncompliance**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RuleDescription**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RuleName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ValueRule**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **WhereClause**








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
Add-CMComplianceSettingWqlQuery -ClassName <String> -DataType {String | Integer | DateTime | FloatingPoint | Version | StringArray | Boolean | IntegerArray} [-Description <String>] [-DisableWildcardHandling] -Existence {MustExist | MustNotExist | Occurs} -ExistentialRule [-ExpectedValue <String[]>] [-ExpressionOperator {And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll | And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll}] [-ForceWildcardHandling] -InputObject <PSObject> -Name <String> -Namespace <String> [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] [-PassThru] -Property <String> [-RuleDescription <String>] -RuleName <String> [-WhereClause <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMComplianceSettingWqlQuery -ClassName <String> -DataType {String | Integer | DateTime | FloatingPoint | Version | StringArray | Boolean | IntegerArray} [-Description <String>] [-DisableWildcardHandling] -ExpectedValue <String[]> -ExpressionOperator {And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll | And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll} [-ForceWildcardHandling] -InputObject <PSObject> -Name <String> -Namespace <String> [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] [-PassThru] -Property <String> [-Remediate] [-ReportNoncompliance] [-RuleDescription <String>] -RuleName <String> -ValueRule [-WhereClause <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMComplianceSettingWqlQuery -ClassName <String> -DataType {String | Integer | DateTime | FloatingPoint | Version | StringArray | Boolean | IntegerArray} [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <PSObject> -Name <String> -Namespace <String> [-NoRule] [-PassThru] -Property <String> [-WhereClause <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
