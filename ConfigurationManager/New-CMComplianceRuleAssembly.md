New-CMComplianceRuleAssembly
----------------------------




### Synopsis
Creates a compliance rule assembly.



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
#### **Culture**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExpectedValue**








|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|false   |named   |False        |ExpectedValues|



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








|Type                        |Required|Position|PipelineInput |Aliases|
|----------------------------|--------|--------|--------------|-------|
|`[ConfigurationItemSetting]`|true    |named   |True (ByValue)|Setting|



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



#### **PublicKeyToken**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



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
Microsoft.ConfigurationManagement.DesiredConfigurationManagement.ConfigurationItemSetting





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMComplianceRuleAssembly -Culture [-DisableWildcardHandling] [-ExpectedValue <String[]>] -ExpressionOperator {And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll} [-ForceWildcardHandling] -InputObject <ConfigurationItemSetting> [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] [-ReportNoncompliance] [-RuleDescription <String>] -RuleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMComplianceRuleAssembly [-DisableWildcardHandling] [-ExpectedValue <String[]>] -ExpressionOperator {And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll} [-ForceWildcardHandling] -InputObject <ConfigurationItemSetting> [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] -PublicKeyToken [-ReportNoncompliance] [-RuleDescription <String>] -RuleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
