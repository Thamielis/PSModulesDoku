New-CMComplianceRuleFileFolderSimple
------------------------------------




### Synopsis
Create a compliance rule for a simple file folder.



---


### Description

Use this cmdlet to create a compliance rule for a simple file folder.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMConfigurationItem](Get-CMConfigurationItem)



* [Add-CMComplianceSettingFile](Add-CMComplianceSettingFile)



* [Get-CMComplianceSetting](Get-CMComplianceSetting)



* [Add-CMComplianceSettingRule](Add-CMComplianceSettingRule)





---


### Examples
#### Example 1
```PowerShell
$ci = Get-CMConfigurationItem -Name "ci1" -Fast

$Result = $ci | Add-CMComplianceSettingFile -Path "C:\" -FileName  "TestFile.exe" -NoRule -Name "AttributeSetting1"

$TestSet = $Result | Get-CMComplianceSetting -SettingName "AttributeSetting1"

$r1 = $TestSet | New-CMComplianceRuleFileFolderSimple -PropertyType SHA1Hash -RuleName "RuleSha1HashEquals" -ExpressionOperator IsEquals -ExpectedValue "s4XuFV2KZldXAMQZ6YEWFv+5zA6ZB982Fbh471TMboc="

$r2 = $TestSet | New-CMComplianceRuleFileFolderSimple -PropertyType Company -RuleName "RuleCompanyEquals" -ExpressionOperator IsEquals -ExpectedValue "Contoso"

$r3 = $TestSet | New-CMComplianceRuleFileFolderSimple -PropertyType ProductName -RuleName "RuleProductNameEquals" -ExpressionOperator IsEquals -ExpectedValue "MyContoso"

$Result | Add-CMComplianceSettingRule -Rule $r1

$Result | Add-CMComplianceSettingRule -Rule $r2

$Result | Add-CMComplianceSettingRule -Rule $r3
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ExpectedValue**

Specify an array of strings to compare the value. The value to compare depends upon the specified PropertyType .






|Type        |Required|Position|PipelineInput|Aliases       |
|------------|--------|--------|-------------|--------------|
|`[String[]]`|false   |named   |False        |ExpectedValues|



#### **ExpressionOperator**

For the ExpectedValue , specify the comparison operator.



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

Specify a configuration item setting object as the target of this rule.






|Type                        |Required|Position|PipelineInput |Aliases|
|----------------------------|--------|--------|--------------|-------|
|`[ConfigurationItemSetting]`|true    |named   |True (ByValue)|Setting|



#### **NoncomplianceSeverity**

Specify the severity level for reports when the rule is noncompliant.



Valid Values:

* None
* Informational
* Warning
* Critical
* CriticalWithEvent






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[NoncomplianceSeverity]`|false   |named   |False        |



#### **PropertyType**

Specify the folder property to compare and assess for compliance. Use the -ExpectedValue parameter to specify the value of this property, and the -ExpressionOperator parameter to specify the means of comparison.


Starting in version 2010, the parameter type changed from FileFolderProperty to SimpleFileFolderProperty type.



Valid Values:

* Company
* ProductName
* SHA1Hash






|Type                        |Required|Position|PipelineInput|
|----------------------------|--------|--------|-------------|
|`[SimpleFileFolderProperty]`|true    |named   |False        |



#### **ReportNoncompliance**

Add this parameter to report noncompliance if this setting instance isn't found.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RuleDescription**

Specify an optional description for this rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RuleName**

Specify the name for this rule.






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
New-CMComplianceRuleFileFolderSimple [-DisableWildcardHandling] [-ExpectedValue <String[]>] -ExpressionOperator {And | Or | Other | IsEquals | NotEquals | GreaterThan | LessThan | Between | NotBetween | GreaterEquals | LessEquals | BeginsWith | NotBeginsWith | EndsWith | NotEndsWith | Contains | NotContains | AllOf | OneOf | NoneOf | SetEquals | SubsetOf | ExcludesAll} [-ForceWildcardHandling] -InputObject <ConfigurationItemSetting> [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] -PropertyType {Company | ProductName | SHA1Hash} [-ReportNoncompliance] [-RuleDescription <String>] -RuleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
