Add-CMComplianceSettingSqlQuery
-------------------------------




### Synopsis
Adds a compliance setting sql query



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
#### **ColumnName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DatabaseName**








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



#### **InputObject**








|Type        |Required|Position|PipelineInput |
|------------|--------|--------|--------------|
|`[PSObject]`|true    |named   |True (ByValue)|



#### **InstanceName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InstanceType**





Valid Values:

* Default
* Named
* All






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[TargetSqlInstance]`|false   |named   |False        |



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



#### **SqlStatementFile**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SqlStatementText**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ValueRule**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



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
Add-CMComplianceSettingSqlQuery -ColumnName <String> -DatabaseName <String> -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean} [-Description <String>] [-DisableWildcardHandling] -Existence {MustExist | MustNotExist | Occurs} -ExistentialRule [-ExpectedValue <String[]>] [-ExpressionOperator {And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll | And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll}] [-ForceWildcardHandling] -InputObject <PSObject> [-InstanceName <String>] [-InstanceType {All | Default | Named}] -Name <String> [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] [-PassThru] [-RuleDescription <String>] -RuleName <String> [-SqlStatementFile <String>] [-SqlStatementText <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMComplianceSettingSqlQuery -ColumnName <String> -DatabaseName <String> -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean} [-Description <String>] [-DisableWildcardHandling] -ExpectedValue <String[]> -ExpressionOperator {And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll | And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll} [-ForceWildcardHandling] -InputObject <PSObject> [-InstanceName <String>] [-InstanceType {All | Default | Named}] -Name <String> [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] [-PassThru] [-ReportNoncompliance] [-RuleDescription <String>] -RuleName <String> [-SqlStatementFile <String>] [-SqlStatementText <String>] -ValueRule [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMComplianceSettingSqlQuery -ColumnName <String> -DatabaseName <String> -DataType {String | DateTime | Integer | FloatingPoint | Version | Boolean} [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <PSObject> [-InstanceName <String>] [-InstanceType {All | Default | Named}] -Name <String> [-NoRule] [-PassThru] [-SqlStatementFile <String>] [-SqlStatementText <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
